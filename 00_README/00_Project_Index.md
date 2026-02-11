## 1. General Information
- Project: Native Search (E-commerce Website)
- Type: Web, Mobile
- Environment:
  - QA: 
  - UAT: 
- Version/Sprint current: Sprint 1

This repository documents the **Native Search** system: requirements, UI mapping, and testing guidance for building a complete search experience (Search UI, Search Engine settings, Filter, Sync, Analytics, Merchandising).

## 2. Scope
Native Search includes these major modules:

- **Search**
  - Storefront Display Setup
    - Instant Search Widget (ISW)
    - Search Result Page (SRP)
  - Search Engine Setup
    - Suggestion Dictionary
    - Stopwords
    - Redirects
    - (Synonyms, General Settings if applicable)
- **Sync**
  - Scheduled / Auto Sync
  - Manual Sync
  - Sync History / Notification (if applicable)
- **Filter**
  - Display Setup
  - Data Settings
    - Filter Cache (sub-feature)
    - Merge Value (sub-feature)
    - Advanced Settings (sub-feature)
- **Merchandising**
  - Scoring System (sub-feature)
  - Merchandise Campaign (sub-feature)
- **Analytics**
  - Search Analytics (sub-feature)
  - Product Analytics (sub-feature)
## 3. Repository Structure (recommended)

## 4. Documentation Principles
Each feature folder should include:

1. **SPEC_*.pdf**  
   Source of truth for logic/flow.
2. **Figma.md**  
   UI mapping based on Figma/exported images:
   - pages/screens
   - components
   - states/empty/loading/error
3. **NOTE_*.md**  
   Convert UI notes (sticky notes / annotations in images) into clear text:
   - concise, implementation-ready
   - aligned to the spec flow
   - avoid adding new logic not shown in UI/spec

## 5. How to Use This Repo
- **BA/PM**: confirm requirements, edge cases, acceptance criteria
- **Designer**: align UI structure and states
- **Dev**: implement based on SPEC + Figma mapping
- **QA**: use `02_Test_Process.md` and per-feature NOTE to validate flows

## 6. Quick Start Checklist (for writing a new feature)
1. Create feature folder under `01_REQUIREMENT/...`
2. Add `SPEC_*.pdf`
3. Export key UI screens into `UI_Export/`
4. Write:
   - `Figma.md` (UI mapping)
   - `NOTE_*.md` (textual notes aligned to spec)
5. Add link/entry into a feature index (optional)

---



