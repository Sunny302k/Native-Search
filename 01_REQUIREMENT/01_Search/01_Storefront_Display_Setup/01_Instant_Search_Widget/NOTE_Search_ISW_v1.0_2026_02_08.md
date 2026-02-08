# NOTE — Instant Search Widget (ISW) — Consolidated Figma Notes
Version: v1.0  
Date: 2026-02-08
Owner: Ha Nguyen
Source: Figma (ISW frames + on-frame notes). **Figma notes are treated as official specs.**

---

## 1) Purpose
This document converts all Figma on-frame notes for **Instant Search Widget (ISW)** into a single, readable text specification for QA/Dev.  
Use it as the baseline for test scenarios, test cases, and requirement review.

---

## 2) Scope
ISW covers:
- Desktop & Mobile behaviors
- Search suggestions + product results in the widget
- Layout/view variants (List/Grid) and responsive behavior
- Without-results state behavior
- Configuration-related flows (e.g., adding products/search terms manually)
- Supporting content sections (e.g., Blog) and Filter Tree behaviors

---

## 3) References (Frame → Source Mapping)
> Fill in file names (or PDF page numbers) that you exported from Figma.

| Ref | Area | Export file / PDF page | Notes |
|---|---|---|---|
| ISW-01 | Desktop preview — choosing layout | `Desktop Preview when choosing layout.png` | Layout variants, products per row |
| ISW-02 | Desktop — without results | `Desktop Preview Without results.png` | Empty state, suggestion behavior |
| ISW-03 | Blog | `Blog.png` | Blog section rules |
| ISW-04 | Filter Tree | `Filter tree.png` | Filter structure + behavior |
| ISW-05 | Add product manually | `Add product manually.png` | Admin/config flow |
| ISW-06 | Add search term manually | `Add search term manually.png` | Admin/config flow + validation |
| ISW-07 | Mobile preview (with/without results) | `Mobile Preview when choosing layout + Without results.png` | Mobile layout + empty state |
| ISW-08 | Product detail / product card variants | `Product Detail.png` | Card fields, enable/disable full |

---

## 4) General Behavior
- ISW appears when the user interacts with the search input (typing / focusing) and displays:
  - **Suggestions** (e.g., categories, terms, blog/content depending on config)
  - **Products** results
- The widget supports multiple **layout/view variants** and different behaviors on Desktop vs Mobile.
- Any rule written as a Figma note is considered **binding spec**.

---

## 5) Desktop — Layout & View Variants (ISW-01)
### 5.1 Supported layouts (Desktop)
- **Layout: 2-col**
- **Layout: Overlay fullwidth**
- **Layout: One column**

### 5.2 Supported views
- **List view**
- **Grid view**

### 5.3 Products-per-row rules
> Confirm from Figma notes and keep these as the source of truth.

- **Layout 2-col**
  - List view: `__` product(s) / row
  - Grid view: `__` product(s) / row
- **Layout Overlay fullwidth**
  - List view: `__` product(s) / row
  - Grid view: `__` product(s) / row
- **Layout One column**
  - List view: `__` product(s) / row
  - Grid view: `__` product(s) / row

### 5.4 “View all products” CTA
- Visibility rule: `TBD`
- Label/text rule: `TBD`
- Click behavior (navigation): `TBD`

### 5.5 Scroll behavior (if applicable)
- When results exceed the visible area:
  - Widget scrolls: `Yes/No` (TBD)
  - “Scroll to the end” behavior: `TBD`

---

## 6) Without Results State (Desktop/Mobile) (ISW-02, ISW-07)
### 6.1 Trigger conditions
- Without-results state occurs when: `TBD` (e.g., no matching products for query)

### 6.2 UI blocks shown in Without Results
- Suggestions list: `TBD`
- Categories list: `TBD`
- Trending / Recently viewed / Popular searches (if configured): `TBD`

### 6.3 Rules & constraints
- Max items per block: `TBD`
- Hide/Show rules when data is empty: `TBD`
- Pagination visibility: `TBD` (usually hidden when no product results)

### 6.4 Click behaviors
- Click suggestion term:
- Click category:
- Click blog item (if present):
- Click “View all products” (if present):

---

## 7) Blog Section (ISW-03)
### 7.1 Visibility rule
- Blog section appears when: `TBD`

### 7.2 Content rules
- Number of blog items shown: `TBD`
- Fields shown (title/thumbnail/snippet/date): `TBD`

### 7.3 Interaction
- Click a blog item navigates to: `TBD`
- Open in same tab vs new tab: `TBD`

### 7.4 Edge cases
- Long titles / missing thumbnail handling: `TBD`

---

## 8) Filter Tree (ISW-04)
### 8.1 Structure
- Parent nodes:
- Child nodes:
- Expand/collapse: `TBD`

### 8.2 Apply behavior
- Clicking a filter:
  - Updates product results in widget: `Yes/No` (TBD)
  - Navigates to SRP: `Yes/No` (TBD)
- Selected state display: `TBD`

### 8.3 Reset rules
- Reset filter action exists: `Yes/No` (TBD)
- Reset trigger (new query / clear search / close widget): `TBD`

---

## 9) Admin/Config — Add Product Manually (ISW-05)
### 9.1 Purpose
- Used to: `TBD` (e.g., pin products, curated list, fallback products)

### 9.2 Flow
1. Open ISW configuration
2. Choose **Add product manually**
3. Search/select product(s)
4. Confirm/Save

### 9.3 Rules
- Max number of products allowed: `TBD`
- Duplicate product handling: `TBD`
- Priority over auto-search results: `TBD`

### 9.4 Edge cases
- No product found
- Out-of-stock product behavior
- Persistence after refresh/save

---

## 10) Admin/Config — Add Search Term Manually (ISW-06)
### 10.1 Purpose
- Used to: `TBD` (e.g., manage popular searches/suggestions, synonyms, curated terms)

### 10.2 Flow
1. Open Search Terms management
2. Add term
3. Save/Confirm

### 10.3 Validation rules
- Min length:
- Max length:
- Allowed characters:
- Trim whitespace rule:
- Duplicate term behavior (reject/merge/overwrite):

### 10.4 Priority rules
- Manual terms priority vs auto terms: `TBD`

---

## 11) Mobile Behavior (ISW-07)
### 11.1 Layout & view
- Mobile supports:
  - **Layout One column — List view**
  - **Layout One column — Grid view**
- Responsive switching rules: `TBD`

### 11.2 With results
- Scroll behavior:
- Layout switching availability:
- CTA behavior:

### 11.3 Without results
- Which blocks appear:
- Limits / ordering:

---

## 12) Product Card / Item Display Rules (ISW-08)
### 12.1 Fields displayed
- Product image
- Product title
- Price / sale price
- SKU (if applicable): `TBD`
- Description (if applicable): `TBD`

### 12.2 Variants (Enable full vs Disable full)
- **Disable full**:
  - Show: `TBD`
  - Truncation rule: `TBD`
- **Enable full**:
  - Additional fields shown: `TBD`
  - Max lines / truncation: `TBD`

### 12.3 Edge cases
- Missing image placeholder
- Very long title handling
- Price formatting/currency
- Accessibility (focus/keyboard) if required

---

## 13) Conflicts / Gaps
- Spec PDF missing but Figma note adds:
- Any conflicts found between documents:
- Decision/confirmation needed from BA/PO:

---

## 14) Open Questions (QA → BA/PO/Dev)
1. `TBD`
2. `TBD`
3. `TBD`

---

## 15) QA Extraction Checklist
- [ ] Layout variants covered (2-col / overlay fullwidth / one column)
- [ ] List/Grid view rules captured
- [ ] Products-per-row rules recorded
- [ ] Without-results rules captured (blocks, ordering, limits)
- [ ] Blog section rules captured
- [ ] Filter Tree behavior captured
- [ ] Add product manually flow + constraints captured
- [ ] Add search term manually flow + validation captured
- [ ] Mobile behavior captured (with/without results)
- [ ] Product card fields + enable/disable full rules captured
