# Scenarios — Redirects

## References
- Requirement: `01_REQUIREMENT/01_Search/02_Search_Engine_Setup/04_Redirect/`
- Spec: `SPEC_Search_Redirects_*.pdf`
- Figma export: `Figma.md` + UI exports
- Rule: Figma Notes = Specs

## RD-01 — View redirects list
- Verify listing, paging, and search behavior

## RD-02 — Create redirect (happy path)
- Input search term(s)
- Input redirect destination (URL)
- Save → verify success + appears in list

## RD-03 — Create redirect validations
- Missing required fields
- Invalid URL formats
- Duplicate rules (if restricted)

## RD-04 — Edit redirect
- Modify term or destination
- Save → verify updated

## RD-05 — Delete redirect
- Confirm dialog
- Verify removed + success toast
