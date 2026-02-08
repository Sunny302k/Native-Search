# figma.md — Search Result Page (SRP)

## Purpose
This document lists the **Figma frames** (and what to review in each) for the **Search Result Page** feature.

## Scope (SRP main components)
SRP includes these main parts: **Header**, **Filter**, **Product**, **Category & Blog**. :contentReference[oaicite:0]{index=0}

## Where SRP data comes from
On SRP, **Product / Category / Blog results** come from the customer search query (shown partially in Instant Search Widget, and fully on SRP). :contentReference[oaicite:1]{index=1}

---

## Frames / Sections to review (recommended order)

### 1) Search Result Page — Overview (Desktop)
**Review checklist**
- Top search input + results summary
- Tabs: Products / Category / Blog (with counts)
- Sort/“Relevance setting” dropdown
- Pagination controls and/or scrolling behavior
- “View as” layout switch (Grid/List)

### 2) Header (Desktop + Mobile)
**Review checklist**
- Default header state
- Search query display rules (if any)
- Tabs layout + counts
- Responsive behavior

### 3) Filter Layout (Desktop) + Filter Layout (Mobile)
**Review checklist**
- Filter groups order and behavior (expand/collapse if any)
- Desktop vs Mobile presentation rules
- Interaction model on mobile (drawer/sheet, apply/reset patterns if designed)

### 4) Product List (Desktop + Mobile)
**Review checklist**
- Layout options: Grid vs List
- Items-per-row rules per breakpoint/layout
- Layout switch UI (“View as”)
- Paging mode: Pagination vs Show more vs Infinite scroll

### 5) Category / Blog
**Review checklist**
- How Category & Blog are shown on SRP
- Sorting/paging rules (if they share logic with products or differ)

### 6) Without Results (Empty state)
**Review checklist**
- Which components appear when there are **no results**
- Trending products block
- Recently viewed products block
- Any CTA logic (install Native Recommender, etc.)

---

## Notes for reviewers
- If you see a “minimum resolution / browser too small” warning in prototypes, treat it as a **design constraint** for desktop testing (set viewport ≥ the designed breakpoint).
- Prefer reviewing **Desktop and Mobile** variants for each section because layout + filter behavior often differs across devices.
