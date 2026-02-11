
## Rule: Figma Notes = Specs
- All notes/annotations on Figma frames are treated as official specs/requirements.
- QA must read and cover Figma notes when creating test scenarios/cases.
- If PDF specs conflict with Figma notes, QA will raise questions for confirmation (do not assume).
# 00_README/01_Naming_Convention.md

# Naming Convention

## 1. Folder Naming
### Rules
- Use **2-digit prefixes** for ordering: `00_`, `01_`, `02_`...
- Use **PascalCase or snake_case with underscores** consistently.
- Prefer **descriptive names** over short names.

### Recommended style
- Folder: `01_Search_Result_Page`, `02_Search_Engine_Setup`, `03_Advanced_Setting`
- Sub-feature folder inside a parent feature: `00_SPEC` for shared specs.

## 2. File Naming

### 2.1 SPEC files
**Format**
- `SPEC_<Domain>_<Feature>_v<Major.Minor>_<YYYY-MM-DD>.pdf`

**Examples**
- `SPEC_Search_SearchResultPage_v1.0_2025-07-16.pdf`
- `SPEC_Filter_v1.0_2025-10-14.pdf`
- `SPEC_Merchandise_v1.0_2025-10-16.pdf`

### 2.2 NOTE files
**Purpose**
- Convert UI annotations/images → clear textual notes
- Must align with the spec flow; do not invent behavior

**Format**
- `NOTE_<Domain>_<FeatureAbbrev>_v<Major.Minor>_<YYYY-MM-DD>.md`

**Examples**
- `NOTE_Search_SRP_v1.0_2025-07-16.md`
- `NOTE_Search_Stopwords_v1.0_2024-05-27.md`
- `NOTE_Search_SuggestionDictionary_v1.0_2026-10-16.md`
- `NOTE_Filter_AdvancedSetting_v1.0_2025-10-14.md`

### 2.3 Figma mapping file
**Format**
- `Figma.md` (fixed name inside each feature folder)

### 2.4 UI exports
- Store UI images under: `UI_Export/`
- Name images by screen/step:
  - `01_ListPage.png`
  - `02_CreateModal_Step1.png`
  - `03_CreateModal_Step2.png`
  - `04_EditModal.png`
  - `05_DeleteDialog.png`
  - `06_EmptyState.png`
  - `07_SuccessToast.png`

## 3. Feature Abbreviation (recommended)
Use short and consistent abbreviations in NOTE files:

- Instant Search Widget: `ISW`
- Search Result Page: `SRP`
- Suggestion Dictionary: `SD` or `SuggestionDictionary`
- Stopwords: `Stopwords`
- Redirects: `Redirects`
- Filter Cache: `FilterCache`
- Merge Value: `MergeValue`
- Advanced Setting: `AdvancedSetting`
- Scoring System: `Scoring`
- Merchandise Campaign: `Campaign`

## 4. Versioning
- `v1.0` for first stable version
- Increase:
  - **minor** (`v1.1`) for additions without breaking logic
  - **major** (`v2.0`) for major changes / rework
- Always include **date** in filenames for traceability.

## 5. Markdown Style Guidelines
- Use `#` for title, `##` for sections, `###` for sub-sections.
- Prefer bullet points and short paragraphs.
- Use checklists for acceptance criteria:
  - `- [ ]` not done
  - `- [x]` done
- Avoid screenshots embedded directly unless necessary; keep images in `UI_Export/`.

## 6. Rule: Figma Notes = Specs
- All notes/annotations on Figma frames are treated as official specs/requirements.
- QA must read and cover Figma notes when creating test scenarios/cases.
- If PDF specs conflict with Figma notes, QA will raise questions for confirmation (do not assume).

---
