# Scenarios — Search Result Page (SRP)

## References
- Requirement: `01_REQUIREMENT/01_Search/02_Search_Result_Page/`
- Spec: `SPEC_Search_SearchResultPage_*.pdf`
- Figma export: `Figma.md` + images in `UI_Export/`
- Rule: Figma Notes = Specs

## SRP-01 — Load SRP with a keyword
- Verify SRP loads with keyword query
- Verify result count display
- Verify tab behavior (Products/Category/Blog if applicable)
- Verify pagination (if present)

## SRP-02 — No results state
- Search keyword that returns 0 results
- Verify empty state messaging and layout (desktop/mobile)

## SRP-03 — Sorting & view modes
- Verify sort control options and behavior
- Verify view mode toggle (grid/list) if supported

## SRP-04 — Filter integration on SRP
- Apply filters and confirm:
  - Product list updates
  - URL update rules (if required)
  - Clear filters works

## SRP-05 — Responsive UI (desktop/mobile)
- Validate layout in both modes
- Validate sticky elements and spacing
