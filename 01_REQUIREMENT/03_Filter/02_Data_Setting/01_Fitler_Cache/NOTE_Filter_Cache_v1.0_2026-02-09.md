# NOTE — Filter Cache

## 1. Purpose (as shown on UI)
- Filter Cache is used to optimize loading speed for pages using Filter
- Cached data is stored per page
- User can manually clear cache when needed

## 2. Filter Cache Page UI

### Header section
- Page title: "Filter Cache"
- Description text explains:
  - Cache helps improve loading speed
  - Clearing cache will refresh filter data

### Cached Pages List
- Section title: Cached Page
- A list of pages currently cached

Observed cached page types:
- Homepage
- Search Result Page

Each row includes:
- Page name
- Action button: "Clear Cache"

### Pagination
- Pagination controls shown at bottom of list
- Supports navigating between cached page records

## 3. Actions

### Clear cache (per page)
- Clicking "Clear Cache" on a row:
  - Clears cache for that specific page only
  - Page remains in the list after clearing

### Clear all cache
- A "Clear All" action is available
- Clears cache for all listed pages at once

## 4. User feedback (from UI)
- After clearing cache:
  - Success feedback is shown (toast / message)
  - Cached list remains visible

## 5. Notes / Observations
- No configuration options inside Filter Cache
- No edit/create flows — only cache management
- Filter Cache is a maintenance / utility feature
