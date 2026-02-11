# Technical Specification: Sync Data Job

## Overview

SyncData is the main orchestrator job that coordinates all data synchronization operations between BigCommerce stores and our search system. It acts as the "conductor" that ensures all data import tasks happen in the correct order and tracks their progress.

**Purpose:** Ensures store data (products, categories, blogs) is accurately synchronized to our search platform.

## What It Does

The Sync Data job serves as the central control point for synchronizing store data. When triggered (either manually or automatically), it:

1. **Validates** that the sync request is legitimate and ready to process
2. **Coordinates** multiple specialized import jobs in the proper sequence
3. **Tracks** the status of the entire synchronization process
4. **Logs** any errors that occur for troubleshooting
5. **Updates** scheduling information for recurring syncs

## Key Concepts

### Batch Management
Each synchronization operation is tracked as a "batch" with:
- **Batch ID**: Unique identifier for tracking
- **Store Hash**: Identifies which BigCommerce store is being synced
- **Type**: What kind of data to sync (products, categories, blogs, or all)
- **Status**: Current state of the synchronization
- **Scheduling Info**: Whether this is a one-time or recurring sync

### Synchronization Types
The system supports several sync types:

| Type | What It Syncs |
|------|---------------|
| **All** | Everything (products, categories, pages, blogs) |
| **Product** | Only product catalog data |
| **Category** | Categories and web pages |
| **Blog** | Blog posts and articles |
| **Stop Words** | Search optimization configuration |
| **Synonyms** | Search enhancement configuration |

## Process Flow

### Phase 1: Validation & Preparation
When a sync job starts, the system first:

1. **Checks if the batch exists** - Verifies the sync request is valid
2. **Verifies status is pending** - Ensures it hasn't already been processed
3. **Extracts batch information** - Gets store details and sync type
4. **Updates status to "Processing"** - Marks the job as actively running

If validation fails, the job immediately stops and throws an error.

### Phase 2: Job Orchestration
The sync process is broken into three sequential phases:

#### Phase 2.1: Configuration Setup
**Purpose:** Generate necessary configuration files for search optimization

- **Stop Word Generation**: Creates lists of common words to exclude from search (e.g., "the", "and", "a")
- **Synonym Generation**: Creates mappings of equivalent terms (e.g., "phone" = "mobile")

These **must complete first** because later steps depend on these configurations.

#### Phase 2.2: Index Creation
**Purpose:** Ensure the search database structure exists

- **Create Index**: Sets up or updates the Elasticsearch index structure
- Only runs if we're importing actual data (products, categories, or blogs)
- Must complete before data import can begin

#### Phase 2.3: Data Import
**Purpose:** Import actual store data into the search system

These jobs run **in parallel** since they're independent:

- **Product Import**: Fetches and indexes all product information
- **Category Import**: Fetches and indexes categories (also includes web pages)
- **Blog Import**: Fetches and indexes blog posts

### Phase 3: Completion & Cleanup
After all jobs are dispatched:

1. **Success Path**:
   - Updates batch status to "Completed"
   - If this is a scheduled sync, updates the next run time

2. **Failure Path**:
   - Logs detailed error information
   - Updates batch status to "Failed"
   - Allows the system to retry if configured

## Status States

Each batch goes through these states:

| Status | Meaning | When It Happens |
|--------|---------|-----------------|
| **Pending** | Waiting to start | Initial state when sync is requested |
| **Processing** | Currently running | Job has started and is dispatching sub-jobs |
| **Completed** | Successfully finished | All sub-jobs were dispatched without errors |
| **Failed** | Encountered errors | Something went wrong during processing |

**Important Note:** "Completed" means the SyncData job successfully dispatched all required jobs. It does NOT mean all the import jobs have finished - those run asynchronously.

## What Can Go Wrong

### Common Failure Scenarios

1. **Batch Not Found**
   - **Cause**: Invalid batch ID provided
   - **Impact**: Job fails immediately
   - **Action**: Verify batch was created correctly

2. **Batch Already Processed**
   - **Cause**: Batch status is not "Pending"
   - **Impact**: Job fails immediately to prevent duplicate processing
   - **Action**: Check if sync already completed or is currently running

3. **Sub-Job Dispatch Failures**
   - **Cause**: Issues creating index, database problems, etc.
   - **Impact**: Batch marked as failed, error logged
   - **Action**: Review error logs for specific cause

### Error Logging
When errors occur, the system logs:
- Which batch failed (Batch ID)
- Which store was being synced (Store Hash)
- Complete error details for debugging
- Timestamp of failure

This information helps engineers troubleshoot issues quickly.

## Monitoring & Tracking

### What to Monitor

**Key Metrics:**
- **Success Rate**: Percentage of batches completing successfully
- **Processing Time**: How long batches take from pending to completed
- **Failure Frequency**: How often syncs fail for each store
- **Queue Depth**: How many jobs are waiting to run

**Alerts to Set Up:**
- High failure rate for a specific store (might indicate store-specific issues)
- Batches stuck in "Processing" status (might indicate hung jobs)
- Repeated failures for same batch (might indicate systematic problem)

### Where to Check Status

**For Individual Syncs:**
- Check the batch management table/dashboard
- Filter by Store Hash to see all syncs for a store
- Look for batches in "Failed" status

**For Overall Health:**
- Monitor success/failure rates across all stores
- Track average processing times
- Review error logs for patterns

## Business Impact

### Why This Matters

**For Search Accuracy:**
- Ensures customers can find products/content through search
- Keeps search results up-to-date with latest store changes
- Optimizes search quality through stop words and synonyms

**For Store Owners:**
- Product updates appear in search quickly
- New products become searchable automatically
- Content changes are reflected in search results

**For Operations:**
- Automated synchronization reduces manual work
- Error tracking helps identify store-specific issues
- Scheduled syncs keep data fresh without intervention

### Performance Characteristics

**Synchronous Operations** (happen immediately):
- Batch validation
- Status updates to database
- Dispatching sub-jobs

**Asynchronous Operations** (happen in background):
- All data import jobs
- Configuration file generation
- Index creation

This design means the SyncData job completes quickly (seconds), while actual data import happens in the background (minutes to hours depending on data volume).

## Scheduled vs. Manual Syncs

### Manual Syncs
- Triggered by admin action or API call
- One-time execution
- Does NOT update next run time

### Scheduled Syncs
- Triggered automatically by cron system
- Recurring (daily, weekly, etc.)
- Updates next run time after completion
- Marked with `is_scheduled = true` flag

## Integration Points

### Upstream (What Triggers This Job)

1. **Manual Admin Actions**: User clicks "Sync Now" in admin panel
2. **API Endpoints**: External systems trigger sync via API
3. **Cron Jobs**: Scheduled recurring synchronizations
4. **Webhook Handlers**: BigCommerce events trigger selective syncs

### Downstream (What This Job Triggers)

1. **GenerateStopWordFileJob**: Configuration generation
2. **GenerateSynonymFileJob**: Configuration generation
3. **CreateIndexJob**: Search index management
4. **ImportProductJob**: Product data synchronization
5. **ImportCategoryJob**: Category/page data synchronization
6. **ImportBlogJob**: Blog data synchronization

## Dependencies

### Critical Dependencies

**For Job to Start:**
- Valid batch record in database
- Batch must be in "Pending" status
- Store hash must be valid

**For Job to Succeed:**
- Queue workers must be running
- Elasticsearch must be accessible
- BigCommerce API must be reachable (for import jobs)
- Configuration files must be writable (for generation jobs)

## Testing Scenarios

### What to Test

**Happy Path:**
1. Create pending batch
2. Dispatch SyncData job
3. Verify status changes to Processing, then Completed
4. Confirm all expected sub-jobs were dispatched

**Error Handling:**
1. Try to sync non-existent batch (should fail)
2. Try to sync already-completed batch (should fail)
3. Simulate sub-job failure (should mark batch as failed and log error)

**Scheduled Syncs:**
1. Create scheduled batch
2. Run sync
3. Verify next run time was updated

## Glossary

- **Batch**: A single synchronization operation tracked from start to finish
- **Store Hash**: Unique identifier for a BigCommerce store
- **Elasticsearch**: The search database system we use
- **Queue Job**: An asynchronous task that runs in the background
- **Dispatch**: To create and queue a job for execution
- **Index**: The search database structure that holds searchable data
- **Stop Words**: Common words excluded from search for better performance
- **Synonyms**: Word mappings that improve search relevance

## Summary

Sync Data is the orchestration layer that ensures store data flows correctly into our search system. It validates requests, dispatches specialized jobs in the right order, tracks progress, and handles errors gracefully. Understanding this job is essential for troubleshooting sync issues, monitoring system health, and planning improvements to the synchronization process.
