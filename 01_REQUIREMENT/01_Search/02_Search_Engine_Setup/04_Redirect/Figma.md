# figma.md — Redirects (Search)

> Source: Figma screens provided + SPEC_Search_Redirects_v1.0_2024-08-23.pdf :contentReference[oaicite:0]{index=0}  
> Goal of this file: describe the UI frames/flows in Figma (what each frame represents) so Dev/QA can follow the screen map quickly.

## Feature scope
**Redirects** allows merchants to define a rule: when a shopper searches a specific **Search term**, they will be redirected to a target **URL** (“Redirect to”).  
This is managed in the Admin UI (Search → Redirects).

---

## Screens / Frames

### 1) Redirects list page (Landing)
**Purpose:** view all redirects and manage them.

**Main elements**
- Page title: **Redirects**
- Primary CTA: **Create new**
- A list/table of redirects with:
  - **Status** toggle (enable/disable redirect)
  - **Search term** column
  - **Redirect to** column (URL)
  - **Actions**: Edit (pencil) and Delete (trash)

**Behaviors**
- Turning **Status** off disables the redirect rule but keeps it in the list.
- **Edit** opens the “Edit redirect” modal.
- **Delete** opens confirmation dialog.

---

### 2) Create new redirect (Modal)
**Purpose:** create one or multiple redirect rules in one save.

**Modal structure**
- Title: **Create new redirect**
- Table-like editor with columns:
  - **Search term**
  - **Redirect to**
- Row actions:
  - Delete row icon (trash) per row
- CTA inside modal:
  - **+ Add new redirect**
- Footer buttons:
  - **Cancel**
  - **Save redirects**

**Key flow shown in Figma**
1. From list page → click **Create new**
2. Modal opens with at least 1 row
3. User can add more rows via **Add new redirect**
4. User fills Search term + Redirect to
5. Click **Save redirects** → success toast + return to list page

---

### 3) Inline validation states (Create modal)
**Purpose:** prevent saving invalid redirects.

**Validation examples shown**
- **Search term** field error state (red highlight + message)
- **Redirect to** field error state (red highlight + message)

> Exact validation rules are defined in the spec; Figma shows the error UI and where messages appear. :contentReference[oaicite:1]{index=1}

---

### 4) Delete redirect confirmation (Dialog)
**Dialog content**
- Title: **Delete redirect?**
- Message: **Deleted redirects cannot be recovered. Do you still want to continue?**
- Buttons: **Delete** / **Cancel**

**After delete**
- Success toast: **Success — Saved changes!**

---

## Notes for implementation mapping
- “Create new redirect” supports **multi-row** creation in one submit.
- Delete can happen:
  - **Delete a row inside the Create modal** (removes the draft row only)
  - **Delete an existing redirect from the list** (requires confirmation dialog)

---
