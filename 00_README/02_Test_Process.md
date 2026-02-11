# 00_README/02_Test_Process.md

# Test Process (Native Search)

## 1. Goal
Provide a consistent way to test Native Search features using:
- SPEC logic (source of truth)
- Figma mapping (UI states and actions)
- NOTE (converted UI annotations → textual rules)

## 2. Roles & Responsibilities
- **BA/PM**: define acceptance criteria and edge cases
- **Developer**: implement per spec
- **QA/Tester**: validate behavior end-to-end and log defects
- **Designer**: confirm UI states match designs

## 3. Test Levels
### 3.1 Smoke Test (fast)
- Navigation to feature works
- Core CRUD works (if applicable)
- No critical UI break / crash
- Basic success & error toasts show correctly

### 3.2 Functional Test (main)
- Validate all flows from spec
- Validate all UI states from Figma
- Validate validations, constraints, and side-effects

### 3.3 Regression Test
- Verify new changes do not break:
  - Search UI output
  - Search Engine behaviors
  - Filter behaviors
  - Merchandising ranking logic
  - Sync scheduling and data freshness

## 4. Test Artifacts
Each feature should have:
- `SPEC_*.pdf`
- `Figma.md`
- `NOTE_*.md`
Optional:
- `TestCases.md` (if the feature is large)
- `Known_Issues.md`

## 5. Standard Test Template (per feature)
Use this structure when writing test cases:

### A. Preconditions
- Store connected
- Data synced
- Feature enabled
- Required permissions available

### B. Test Data
- Example query terms
- Product/category/blog samples
- URLs for redirect tests
- Stopwords list samples
- Suggestions list samples

### C. Test Cases
Each test case should include:
- **ID**
- **Feature/ Sub- Feature**
- **Title**
- **Steps**
- **Expected Result**
- **Notes/References** (SPEC section / UI screen name)

### D. Acceptance Criteria Checklist
- [ ] All required flows pass
- [ ] Validation rules pass
- [ ] Empty / error / loading states correct
- [ ] Permissions and limits correct
- [ ] UI matches design (layout/text/buttons)
- [ ] No critical bugs

## 6. Common Test Coverage (Native Search)
### 6.1 CRUD + Validation pattern
For admin features like Suggestion Dictionary / Stopwords / Redirects:
- Create
- Edit
- Delete
- Toggle enable/disable (if present)
- Validation:
  - required fields
  - duplicates
  - invalid format (URL, etc.)
  - max length / limits
- Feedback:
  - success toast
  - error message
  - loading state

### 6.2 Search UI validation
For SRP/ISW:
- Search term input and submit
- Result count and pagination
- Sorting
- Tabs (Products/Category/Blog if present)
- Empty results
- Filter interactions (apply/clear)
- Responsive views (desktop/mobile switch)

### 6.3 Filter validation
For filter settings:
- Filter nodes visibility rules
- Product count display rules
- URL structure changes
- Shorten URL behavior
- Refine-by block behavior
- Smart filter search behavior

### 6.4 Merchandising validation
For scoring and campaign:
- Base score changes apply correctly
- Variant/Product score relationship rules respected
- Bulk edit conditions filter correct product sets
- Campaign start/end behavior correct
- Priority and conflicts handled (if defined in spec)

### 6.5 Sync validation
- Manual sync triggers job
- Scheduled sync runs as configured
- Data changes reflect in search results after sync
- Sync status/history accurate

## 7. Bug Reporting Standard
When logging a bug, always include:
- **Title**: concise and specific
- **Environment**: staging/prod, browser, account
- **Steps to reproduce**
- **Expected vs Actual**
- **Screenshots/recording**
- **Spec reference**: section/page
- **Severity**: blocker/critical/major/minor
- **Priority**: P0–P3

## 8. Definition of Done (DoD) for a Feature
A feature is “Done” when:
- [ ] All test cases pass (smoke + functional)
- [ ] No P0/P1 issues open
- [ ] Docs updated (Figma.md + NOTE + spec references)
- [ ] UI matches design (reviewed/approved)
- [ ] Regression on related modules passed

---
