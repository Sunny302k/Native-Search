# note.md — Merchandise Campaign

## 1. Purpose

Merchandise Campaign allows merchants to:
- Control product ranking, visibility, and score
- Apply changes in specific contexts:
  - Search keywords
  - Category pages
  - Entire store
- Run campaigns within a defined time period

---

## 2. Campaign Structure

Campaign = Trigger + Execution

---

## 3. Trigger Types

### 3.1 Trigger by Keywords
- Matches user search terms
- Automatically includes synonyms from Synonyms Dictionary
- Applies on Search Result Page

### 3.2 Trigger by Category
- Matches selected categories
- Applies on corresponding Category Pages

### 3.3 Trigger by All
- No condition required
- Applies to all product listing pages

---

## 4. Execution Overview

Execution defines actions applied to products when trigger conditions are met.

---

## 5. Action Groups

### 5.1 Display Actions

- Pin: Fix product position
- Hide: Remove product from list
- Bury: Push product to bottom
- Filter: Display only selected products

**Characteristics**
- Do not participate in global sorting
- Remain unchanged after sync
- Subject to cross-action rules

---

### 5.2 Score Actions

- Boost: Increase product score
- Deboost: Decrease product score

**Characteristics**
- Participate in sorting
- Final position depends on product score
- Recalculated after sync

---

## 6. Cross-action Rules (Display Actions)

- One display action per product at a time
- New display action overrides existing one
- System shows confirmation before override

---

## 7. Filter Action Notes

- Applying Filter action resets all display actions
- Score actions remain unaffected

---

## 8. Additional Conditions

- Customer condition: apply campaign to specific customer groups
- Cart condition: apply based on cart state
- Conditions are optional

---

## 9. Post-sync Logic

- Campaigns are re-evaluated after each sync
- Newly matched products automatically receive actions
- Users are notified when campaign results change

---

## 10. Common Attributes Used in Rules

- Product title
- Category
- Product type
- Brand
- Price
- Inventory status
- Condition
- Featured status
- Purchasability
- Options / Custom fields
- Review rating
