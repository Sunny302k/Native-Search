# figma.md — Search_Stopwords

## Figma file
- Design file: Searching (Stopwords)
- Link: https://www.figma.com/file/dHTNp9Dd43Sbzy0hNWGMUC/Searching?type=design&node-id=1%3A6&mode=design&t=IGzVjswUVK14vx7B-1 :contentReference[oaicite:1]{index=1}

## Screens / flows included
> Naming below follows the screenshots you provided in this conversation.

1. **Stopwords List (Admin page)**
   - List/table view of user-managed stopwords (manual source).
   - Controls: create new stopword, delete stopword (confirmation).

2. **Create New Stop Word (Modal)**
   - Modal to add a stopword (manual source).

3. **Delete Stop Word (Confirmation)**
   - Confirm deletion of an existing stopword (manual source).

4. **Note / Default stopwords list (Onboarding)**
   - When a merchant installs the app, a default list of stopwords is pre-added (manual source).

## UX notes (what matters for build)
- **Two sources of stopwords exist**
  - App global stopwords (system-collected): always applied, **not visible** in admin UI.
  - Merchant manual stopwords: visible in admin UI; created manually or via CSV import. :contentReference[oaicite:2]{index=2}
