# Suggestion Dictionary (Autocomplete Suggestions) — figma.md

## Overview
**Suggestion Dictionary** lets merchants control what shoppers see first in the Instant Search autocomplete by:
- Defining **trigger search terms** (what the shopper types)
- Mapping them to **prioritized suggestions** (what the widget should suggest first)
- Managing the list via **Create / Edit / Delete** flows

---

## Screens & Frames

### 1) Suggestion — Main page
**Purpose:** View and manage all suggestion rules.

**Header / Tour block**
- Title: **Suggestion**
- Collapsible tour: **What is suggestion?**
- Supporting copy (tour): Explains boosting specific suggestions so they appear at the top when customers type in the Instant Search widget. Includes an example.

**Suggestion List**
- Section title: **Suggestion List**
- Search input placeholder: **Search keyword, suggestion**
- Primary CTA: **Create new**

**Table columns**
- **Status**
- **When user search**
- **Do suggestion**
- **Action**

**Row patterns**
- “When user search” shown as chips/tags (e.g., `shoes`, `running shoes`, `trail shoes`)
- “Do suggestion” displayed as a ranked list (1,2,3,…) and may show `+X more`
- Status uses a toggle switch (on/off)
- Actions include icons for **Edit** and **Delete**

**Pagination**
- Footer pagination with **Prev / page numbers / Next**

---

### 2) Create new suggestion — Modal flow
**Entry point:** Click **Create new** on the main page  
**Container:** Center modal with stepper

#### Step 1 — Add search term(s)
- Modal title: **Create new suggestion**
- Stepper:
  - **1 Add search term(s)** (active)
  - **2 Prioritize suggestions**
- Section label: **When user search**
- Input(s) for search terms + CTA: **Add new term**
- Footer buttons: **Cancel** / **Next**

#### Step 2 — Prioritize suggestions
- Stepper:
  - **1 Add search term(s)** (done)
  - **2 Prioritize suggestions** (active)
- Section label: **Do suggestion**
- List of suggestion items (sortable / prioritized)
- Option toggle: **Apply to other search term having this suggestion**
- Footer buttons: **Cancel** / **Save**

**Success feedback**
- Toast: **Success — Saved changes!**

---

### 3) Edit suggestion — Modal flow
**Entry point:** Click **Edit** icon in a row  
**Same stepper structure as Create**

#### Step 1 — Add search term(s)
- Modal title: **Edit suggestion**
- Pre-filled “When user search” terms (editable)
- CTA: **Add new term**
- Footer buttons: **Cancel** / **Next**

#### Step 2 — Prioritize suggestions
- Pre-filled “Do suggestion” list (editable / re-order)
- Option toggle: **Apply to other search term having this suggestion**
- Footer buttons: **Cancel** / **Save**

**Success feedback**
- Toast: **Success — Saved changes!**

---

### 4) Delete suggestion — Confirmation
**Entry point:** Click **Delete** icon in a row

**Dialog**
- Title: **Delete suggestion?**
- Warning copy: Deletion is permanent / cannot be recovered.
- Actions: **Delete** / **Cancel**

**After delete**
- Toast: **Success — Saved changes!**

---

## Interaction Notes (Implementation-facing)
- Create/Edit uses the same 2-step modal + validation gating **Next** until the step 1 requirement is met.
- “Do suggestion” order represents priority (top = highest).
- “Apply to other search term…” toggle affects whether prioritized suggestions are reused across other search terms that share them.
- Table “Status” toggle enables/disables a rule without deleting it.
