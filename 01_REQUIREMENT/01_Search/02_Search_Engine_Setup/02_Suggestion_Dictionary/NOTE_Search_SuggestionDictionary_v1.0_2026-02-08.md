# NOTE — Suggestion Dictionary (Autocomplete Suggestions)

> Purpose of this note: convert the UI content (Figma screenshots) into text that can be reused in spec/docs.  
> Focus: labels, microcopy, placeholders, button names, dialog/toast messages (image → text).

---

## Page: Suggestion (Main)

### Tour / Help block
- **What is suggestion?**
- **Use suggestion to guide what shoppers see first**
  - Boost specific suggestions so they appear at the top when customers type in the instant search widget.
  - Example explanation: when a shopper types something (e.g., “running…”), the prioritized term appears first to guide discovery.

### Section: Suggestion List
- Search input placeholder: **Search keyword, suggestion**
- Primary button: **Create new**

### Table headers
- **Status**
- **When user search**
- **Do suggestion**
- **Action**

### Row content pattern (display rules)
- **When user search**: shown as keyword chips/tags (e.g., `shoes`, `running shoes`, `trail shoes`)
- **Do suggestion**: numbered list of suggestions; may display `+X more` for overflow
- **Action**: icons for **Edit** and **Delete**
- **Status**: toggle switch on/off

### Pagination (footer)
- **Prev** / page numbers / **Next**

---

## Modal: Create new suggestion

### Stepper (top)
- **1 Add search term(s)**
- **2 Prioritize suggestions**

### Step 1 — Add search term(s)
- Modal title: **Create new suggestion**
- Label: **When user search**
- CTA: **Add new term**
- Footer buttons: **Cancel** / **Next**

### Step 2 — Prioritize suggestions
- Label: **Do suggestion**
- Toggle label: **Apply to other search term having this suggestion**
- Footer buttons: **Cancel** / **Save**

### Toast (after Save)
- **Success**
- **Saved changes!**

---

## Modal: Edit suggestion

### Stepper (top)
- **1 Add search term(s)**
- **2 Prioritize suggestions**

### Step 1 — Add search term(s)
- Modal title: **Edit suggestion**
- Label: **When user search**
- CTA: **Add new term**
- Footer buttons: **Cancel** / **Next**

### Step 2 — Prioritize suggestions
- Label: **Do suggestion**
- Toggle label: **Apply to other search term having this suggestion**
- Footer buttons: **Cancel** / **Save**

### Toast (after Save)
- **Success**
- **Saved changes!**

---

## Dialog: Delete suggestion

- Title: **Delete suggestion?**
- Warning: **Deleted suggestion cannot be recovered. Do you still want to continue?**
- Buttons: **Delete** / **Cancel**

### Toast (after Delete)
- **Success**
- **Saved changes!**
