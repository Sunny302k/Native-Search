# Figma Reference — Merge Value

## Feature scope
- Feature: Merge Value
- Parent feature: Filter
- Purpose: Allow merging multiple filter option values into a single display value

## Entry point
- Navigation: Filter → Merge Value (under Filter Settings / Tools)

## Screens & flows

### 1. Merge Value Overview Page
- Displays introduction / description about Merge Value
- Shows list of existing merge groups (if any)
- Primary CTA: Create new merge value

### 2. Create Merge Value — Select Filter
- Modal / page where user selects:
  - Filter type
  - Filter attribute to apply merge
- Continue button to proceed

### 3. Create Merge Value — Select Values
- User selects multiple filter option values
- Selected values will be merged into one value
- Supports selecting many values

### 4. Create Merge Value — Configure Display
- Input for merged value name (display name)
- Shows preview of merged values
- Save action

### 5. Merge Value List Page
- Displays list of created merge values
- Each row shows:
  - Filter
  - Merged value name
  - Included values
  - Status (on/off)
  - Actions: Edit / Delete

### 6. Edit Merge Value
- Same flow as Create
- Pre-filled data

### 7. Delete Merge Value
- Confirmation dialog
- Success feedback after deletion

## Notes
- Figma focuses on UI flow and user interaction
- Merge logic execution is defined in spec, not in Figma
