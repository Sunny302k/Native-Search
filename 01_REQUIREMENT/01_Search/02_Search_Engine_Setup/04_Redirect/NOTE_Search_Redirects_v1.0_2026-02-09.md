# NOTE_Redirects.md — Redirects (Text extracted from Figma)

> Goal of this file: convert the information that appears in the Figma notes/UI into text, aligned with the spec flow. :contentReference[oaicite:2]{index=2}

## A) Redirects — Create flow (Create new redirect)

### A1. Entry point
- On **Redirects** page, click **Create new** → open modal **Create new redirect**.

### A2. Create modal — UI text & controls
- Modal title: **Create new redirect**
- Columns/fields:
  - **Search term**
  - **Redirect to**
- Actions:
  - **+ Add new redirect** (adds a new empty row)
  - Row delete icon (trash) (removes that row from the draft list)
- Footer:
  - **Cancel**
  - **Save redirects**

### A3. Save success
- After clicking **Save redirects** with valid inputs:
  - Return to **Redirects** list page
  - Show toast: **Success — Saved changes!**

### A4. Validation / error states (as shown in Figma)
- If a row contains invalid data, that row’s field is highlighted in red and shows an inline error message.
- Error cases shown:
  1) **Duplicate Search term**  
     - If **Search term** is duplicated (same term appears in another row / existing redirects), show error on the field.
  2) **Invalid Redirect to URL format**  
     - If **Redirect to** is not a valid URL format, show error on the field.

> Figma note indicates these errors are checked on Save and displayed inline at the corresponding row/field.

---

## B) Redirects — Delete flow (Delete redirect)

### B1. Delete existing redirect (from list)
- Click **Delete** (trash) on a redirect row → open confirmation dialog.

### B2. Confirmation dialog — text
- Title: **Delete redirect?**
- Message: **Deleted redirects cannot be recovered. Do you still want to continue?**
- Buttons:
  - **Delete**
  - **Cancel**

### B3. Delete success
- After clicking **Delete**:
  - The redirect is removed from the list
  - Show toast: **Success — Saved changes!**

---

## C) Draft-row delete inside Create modal
- Clicking the trash icon on a row inside **Create new redirect**:
  - Removes the row from the modal draft list
  - Does **not** show the global delete confirmation dialog (this is not deleting persisted data yet)

---

## D) Strings checklist (for i18n / QA)
- Redirects
- Create new
- Create new redirect
- Search term
- Redirect to
- Add new redirect
- Cancel
- Save redirects
- Delete redirect?
- Deleted redirects cannot be recovered. Do you still want to continue?
- Delete
- Success
- Saved changes!

---
