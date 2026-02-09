# Figma Reference — Filter Cache

## Feature scope
- Feature: Filter Cache
- Parent feature: Filter
- Purpose: Manage cached pages related to Filter results

## Entry point
- Navigation: Filter → Filter Cache

## Screens included

### 1. Filter Overview Page
- Filter Cache is shown as a card / section under Filter Settings
- Clicking "Filter Cache" navigates to Filter Cache management page

### 2. Filter Cache Page
- Page title: Filter Cache
- Intro / helper text explaining cache purpose
- Displays list of cached pages

### 3. Cached Pages List
- Each cached item represents a page using Filter
- Observed cached page types:
  - Homepage
  - Search Result Page
  - (Other storefront pages using Filter)

### 4. Cache Actions
- Clear cache per page (individual action)
- Clear all cache (global action)

## Notes
- This Figma only shows UI and available actions
- Cache behavior / invalidation logic is referenced in spec, not defined in Figma
