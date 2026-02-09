# NOTE — Scoring System (Merchandising)

## Purpose
Scoring System controls how products are ranked on Search Result Page and Category Page by combining multiple score components.

---

## Score Components

### 1. Base Score
- Default score set manually by merchant
- Editable via:
  - Single product edit
  - Bulk edit by conditions

---

### 2. Self-learning Score
- Automatically calculated by system
- Accumulated over time (all-time)
- Read-only for merchant

---

### 3. Merchandise Campaign Score
- Score added by active merchandising campaigns
- Characteristics:
  - Only applied within campaign active period
  - Not permanently added into base score
  - Displayed as a separate score component

---

## Product vs Variant Score Logic

- Product score = **average score of all variants**
- If variant score is updated:
  - Product score updates automatically
- If product score is updated:
  - That score is propagated and saved to all variants

---

## Ways to Adjust Base Score

### Method 1: Single Product Adjustment
- User clicks **Edit** on a product
- Popup modal appears
- Adjust base score via slider
- Save to apply immediately

---

### Method 2: Bulk Edit by Conditions
- User enters Bulk Edit flow
- Defines conditions (similar to product match rules)
- System filters and returns matching products
- From filtered list:
  - Adjust base score for all products
  - Or adjust individually per product
- Changes affect only selected products

---

## Campaign Impact (High-level)
- Campaigns affect product ranking temporarily
- Campaign score:
  - Does not overwrite base score
  - Is calculated separately
- Final product ranking score = combined result of:
  - Base score
  - Self-learning score
  - Campaign score (if active)

---

## Important Clarifications
- Editing base score does NOT remove campaign score
- Removing campaign reverts ranking to base + self-learning scores
- All score changes reflect immediately in product ranking after save
