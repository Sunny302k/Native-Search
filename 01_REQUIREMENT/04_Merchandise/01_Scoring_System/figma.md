# Figma — Scoring System (Merchandising)

## Entry point
- Sidebar → Merchandising
- Section: **Product ranking score**
- Actions:
  - View product ranking details
  - Setup base score
  - Manage product ranking

## Main Screens

### 1. Merchandising Overview
- Entry screen for merchandising features
- Section "Product ranking score":
  - Shows explanation about ranking control
  - CTA buttons:
    - Setup base score
    - Manage product ranking

---

### 2. Manage Product Ranking
- List of products with ranking-related information
- Columns include:
  - Product
  - Base score
  - Self-learning score
  - Merchandise campaign score (if any)
  - Final score (read-only)
- Action per row:
  - Edit base score (single product)

---

### 3. Edit Base Score — Single Product
- Triggered by clicking **Edit** on a product row
- Modal dialog:
  - Slider to adjust base score
  - Shows current score value
- Actions:
  - Cancel
  - Save

---

### 4. Bulk Edit Base Score
- Entry via **Bulk edit** button
- Flow:
  1. Select products via conditions (product match rules)
  2. Preview matched product list
  3. Adjust base score:
     - Apply same score to all products
     - Or adjust individually
- Final step:
  - Save changes

---

### 5. Setup Base Score Page
- Table view of products
- Supports:
  - Sorting by product name
  - Sorting by stock
  - Sorting by base score
- Inline edit available per product
- Bulk edit supported

---

### Notes on Display
- Product score shown as composition of:
  - Base score
  - Self-learning score
  - Campaign score (if applied)
- Campaign score is displayed separately and not merged permanently into base score
