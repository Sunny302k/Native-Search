# Scenarios — Suggestion Dictionary

## References
- Requirement: `01_REQUIREMENT/01_Search/02_Search_Engine_Setup/02_Suggestion_Dictionary/`
- Spec: `SPEC_Search_AutocompleteSuggestions_*.pdf`
- Figma export: `Figma.md` + UI exports
- Rule: Figma Notes = Specs

## SD-01 — View suggestion list
- Verify table columns, pagination, search box
- Verify enable/disable (if present)

## SD-02 — Create suggestion (happy path)
- Add search term(s)
- Add suggestion list
- Save → verify success toast + item appears in list

## SD-03 — Create suggestion validations
- Missing required fields
- Duplicate terms
- Limits (max items, max length) per spec/figma notes

## SD-04 — Edit suggestion
- Edit search terms and suggestions
- Save → verify changes applied

## SD-05 — Delete suggestion
- Confirm dialog
- Delete → verify removed and toast shown
