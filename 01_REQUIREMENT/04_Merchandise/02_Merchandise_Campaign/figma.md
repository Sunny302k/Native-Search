# figma.md — Merchandise Campaign

## 1. Entry point

**Menu:**  
Merchandising → Manage merchandise campaign

**Landing screen:**
- List all existing campaigns
- Primary CTA: **Create campaign**
- Row actions:
  - Edit
  - Duplicate (if available)
  - Delete
  - Toggle Active / Inactive

---

## 2. Campaign List Screen

### UI elements
- Campaign list table includes:
  - Campaign name
  - Trigger type
  - Status (Active / Inactive / Expired)
  - Start date – End date
  - Action summary
  - Row actions

### States
- Empty state:
  - Instruction message
  - Button **Create campaign**
- Expired campaign:
  - Marked as “Expired”
  - Not applied on storefront

---

## 3. Create / Edit Campaign – Overall Flow

Campaign setup consists of two main sections:
1. Trigger setup
2. Execution setup

Buttons:
- Cancel
- Save campaign

---

## 4. Trigger Setup

### 4.1 Trigger type selection
Available trigger types:
- Trigger by Keywords
- Trigger by Category
- Trigger by All

---

### 4.2 Trigger by Keywords

**UI**
- Keyword input field
- Support multiple keywords
- Display added keywords as a list

**Behavior**
- Match search terms entered by users
- Automatically include synonyms from Synonyms Dictionary

**Apply location**
- Search Result Page

---

### 4.3 Trigger by Category

**UI**
- Category selector (tree or list)
- Multiple categories supported

**Apply location**
- Selected Category Pages

---

### 4.4 Trigger by All

**UI**
- No additional input

**Behavior**
- Apply campaign to:
  - Search Result Page
  - Category Page
  - All product listing pages

---

## 5. Execution Setup

Execution defines actions applied to products when trigger conditions are met.

Execution includes:
1. Additional Conditions (optional)
2. Action type
3. Apply target (product-based or rule-based)

---

## 6. Additional Conditions (Optional)

### 6.1 Customer condition
- Apply campaign to selected customer groups only

### 6.2 Cart condition
- Apply campaign based on cart conditions (if configured)

---

## 7. Action Setup

Actions are divided into two groups.

---

### 7.1 Display Actions

**Types**
- Pin
- Hide
- Bury
- Filter

**Behavior**
- Products do not participate in global sorting
- Display order remains unchanged after sync

**Apply options**
- Fixed product selection
- Rule-based selection

---

### 7.2 Score Actions

**Types**
- Boost
- Deboost

**Behavior**
- Products still participate in sorting
- Position depends on calculated product score
- Score recalculated after sync

---

## 8. Cross-action Rules

**Scope:** Display actions only

- Each product can have only one display action at a time
- Applying a new display action overrides the existing one
- System shows override confirmation dialog

Display actions and score actions can coexist.

---

## 9. Filter Action – Special Rule

- Applying Filter action resets all existing display actions
- Does not affect score actions

---

## 10. Campaign Lifecycle

**Statuses**
- Draft
- Active
- Expired

**Time-based behavior**
- Campaign applies only when:
  start_date ≤ current_time ≤ end_date

---

## 11. Post-sync Behavior

After each successful sync:
1. Re-evaluate all active campaigns
2. Detect product list changes
3. Auto-apply rules to newly matched products
4. Notify user if campaign result changes
