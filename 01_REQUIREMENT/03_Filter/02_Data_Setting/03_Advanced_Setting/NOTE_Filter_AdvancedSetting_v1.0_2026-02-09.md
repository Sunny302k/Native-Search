# NOTE — Advanced Settings (Filter)

## 1. Overview
Advanced Settings allow users to control how filters are displayed and behave on storefront pages, including:
- Visibility of filter options
- URL structure
- Display of selected filters
- Search behavior inside filter blocks

---

## 2. Show smart filter search

- Toggle default: OFF
- When toggle is ON:
  - A search input appears at the top of filter options
  - Allows users to search within filter values
- Applies only to:
  - Filter nodes using list or grid selection type
- Supported on:
  - Desktop
  - Mobile

---

## 3. Show product count

- Toggle controls whether product count is shown next to filter values
- When ON:
  - Each filter option displays a product count
- When OFF:
  - Product count is hidden from UI

---

## 4. Show Refine by block

- Toggle default: OFF
- When ON:
  - A "Refine by" block is displayed above filter list
  - Shows all selected filter values
  - Each selected value has a remove (x) icon
  - A "Clear all" option is available
- The block allows users to:
  - Review selected filters
  - Remove filters without scrolling back to filter list
- Supported on:
  - Desktop
  - Mobile

---

## 5. Show all irrelevant values (product count = 0)

- Toggle default: OFF
- When ON:
  - Filter options with product count = 0 are displayed
- When OFF:
  - Filter options with product count = 0 are hidden

---

## 6. Hide filter options with only one filter option value

- Toggle default: OFF
- When ON:
  - Filter options with product count = 1 are hidden
- Used to reduce noise when a filter has only one applicable value

---

## 7. Shorten URL when selecting multiple filter option values

- Toggle controls URL format on storefront
- When multiple filter values are selected:
  - Long-form URLs can become complex
- When toggle is ON:
  - URL is shortened
  - URL becomes more SEO-friendly
- UI shows comparison:
  - Old URL format: `?filter[Color_3][]=100`
  - New URL format: `?Color_3=100`
  - SEO-friendly URL: `?Color=Grey`

---

## 8. Change label of Refine By button on mobile

- Applies only on Mobile view
- Toggle changes label behavior when user taps Refine By
- Affects UI text only

---

## 9. Preview behavior

- Preview panel supports:
  - Desktop view
  - Mobile view
- Preview reflects:
  - Toggle ON / OFF states
  - Visual changes immediately

---

## 10. Save Changes

- Changes are not applied until user clicks "Save Changes"
- Save button is located at top right of Advanced Settings page
