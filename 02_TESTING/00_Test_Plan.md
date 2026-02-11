# Native Search — Test Plan

## 1. Purpose
This test plan defines the scope, approach, environments, test data, and quality gates to validate the **Native Search** system (Admin + Storefront behavior) before release.

## 2. References
- `00_README/00_Project_Index.md`
- `01_REQUIREMENT/` (all specs, figma exports, and notes)
- **Rule: Figma Notes = Specs**
  - All notes/annotations on Figma frames are treated as official requirements.
  - QA must read and cover Figma notes when creating test scenarios/cases.
  - If PDF specs conflict with Figma notes, QA will raise questions for confirmation (do not assume).

## 3. Scope
### In scope
- Search features in `01_REQUIREMENT/01_Search/`
- Search Engine Setup: suggestions, stopwords, redirects, general settings
- Search Result Page UI behavior (desktop/mobile) and states
- Filter sub-features (Filter Cache, Merge Values, Advanced Settings) if enabled by the project
- Sync flows (Auto sync / Manual sync) if part of current milestone
- Merchandising: scoring system + campaign (if included in milestone)

### Out of scope (example)
- Non-related admin modules outside Native Search
- Non-functional testing not requested (penetration, compliance) unless explicitly added

## 4. Test Types
- Smoke test (critical path)
- Functional test
- UI/UX & layout test (responsive + states)
- Integration test (Admin settings → Storefront behavior)
- Regression test (after changes)
- Negative test (validation, edge cases)
- Basic performance sanity check (page load, search response timing by observation)

## 5. Environments
List the environments used during testing.

- Admin URL:
- Storefront URL:
- Theme(s) / template(s) (if relevant):
- API base URL (if relevant):
- Build/Release version:

## 6. Roles & Responsibilities
- QA:
  - Create scenarios/cases from specs + figma notes
  - Execute test runs and report issues
  - Maintain regression suite
- PM/PO:
  - Confirm requirement questions
  - Approve scope changes
- Dev:
  - Fix issues, provide build notes
  - Confirm expected behavior for ambiguous cases

## 7. Entry Criteria
- Specs available (PDF + Figma + Notes)
- Test environment stable and accessible
- Feature flags/configs for test clearly documented
- Seed data prepared (products, collections, tags, pages/blog if needed)

## 8. Exit Criteria (Quality Gates)
- 100% pass for smoke tests
- No open **Blocker/Critical** bugs
- All High bugs have workaround or approved defer
- Regression suite executed for impacted areas
- Known issues documented

## 9. Test Data Requirements
Minimum recommended dataset:
- Products: at least 100+ with variants
- Categories/Collections: 10+
- Attributes for filters: Color/Size/Price/Brand/Availability
- Blog posts/pages (if SRP has Blog/Category tabs)
- Redirect rules, stopwords, suggestion dictionary entries (for validation)

## 10. Bug Reporting Format
Use: `02_TESTING/03_Bug_Template.md`

## 11. Test Deliverables
- Test Scenarios: `02_TESTING/01_Test_Scenarios/`
- Test Cases: `02_TESTING/02_Test_Cases/`
- Bug reports (tool-based) + summary in test report
- Test execution summary (optional): `02_TESTING/05_Test_Report.md`
