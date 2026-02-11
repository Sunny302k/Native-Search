# Test Data — Native Search

## Purpose
This folder stores seed data and reusable inputs for testing.

## Recommended contents
- `keywords_positive.txt` (keywords that should return results)
- `keywords_negative.txt` (keywords expected to return 0 results)
- `stopwords_default.txt`
- `redirect_rules.csv`
- `suggestion_dictionary.csv`

## Notes
- Keep test data versioned with the requirement/spec version when possible.
- If data differs per environment, create subfolders:
  - `staging/`
  - `uat/`
  - `prod-sandbox/`
