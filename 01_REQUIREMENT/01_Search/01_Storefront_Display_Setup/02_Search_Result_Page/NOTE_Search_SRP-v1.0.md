# NOTE_Search_SRP-v1.0.md — Search Result Page (SRP)
> Source: Figma + PDF spec “[Spec] Search Result Page” (2025-07-16). :contentReference[oaicite:2]{index=2}  
> Goal: Convert design notes into a single, implementation-friendly requirement document.

---

## 1) Overview
The Search Result Page (SRP) displays full results for a user search query, expanding on what is partially shown in Instant Search Widget. SRP includes:
- Header
- Filter
- Product results
- Category & Blog results :contentReference[oaicite:3]{index=3}

**Data rule**
- Product / Category / Blog results are returned from the customer search query; SRP shows the full set for that query. :contentReference[oaicite:4]{index=4}

---

## 2) Sorting (Relevance Setting)
SRP supports the following sort options. :contentReference[oaicite:5]{index=5}

### 2.1 Sort options
- **Relevance**
  - Sort by similarity score to the search query. :contentReference[oaicite:6]{index=6}

- **Best selling**
  - Sorting logic is the same as “Trending Products”. :contentReference[oaicite:7]{index=7}

- **Title: A–Z**
  - Product name ascending. :contentReference[oaicite:8]{index=8}

- **Title: Z–A**
  - Product name descending. :contentReference[oaicite:9]{index=9}

- **Price: Low–High**
  - Sort by product price.
  - If a product has multiple variants, use the **highest variant price** for sorting. :contentReference[oaicite:10]{index=10}

- **Price: High–Low**
  - Reverse of Low–High. :contentReference[oaicite:11]{index=11}

- **Date: Newest–Oldest** :contentReference[oaicite:12]{index=12}
- **Date: Oldest–Newest** :contentReference[oaicite:13]{index=13}

- **Discount: Highest–Lowest**
  - Sort by discount percentage from high to low.
  - Products without discount fall back to **Relevance** ordering. :contentReference[oaicite:14]{index=14}

- **Review: Highest–Lowest** :contentReference[oaicite:15]{index=15}

> Open question (needs clarification): Date sorting definition and Review sorting definition are listed but not fully described in the spec. :contentReference[oaicite:16]{index=16}

---

## 3) Paging & Scrolling
SRP supports the following paging modes. :contentReference[oaicite:17]{index=17}

### 3.1 Pagination
- Standard pagination UI is available. :contentReference[oaicite:18]{index=18}

### 3.2 Show more
- Loads `5 * {number_of_products_per_row}` products per load. :contentReference[oaicite:19]{index=19}

### 3.3 Infinite scroll
- Shows a loading indicator (GIF loading).
- Loads `5 * {number_of_products_per_row}` products per load. :contentReference[oaicite:20]{index=20}

> Implementation note: `{number_of_products_per_row}` depends on layout (Grid/List) and breakpoint (Desktop/Mobile) as designed in Figma.

---

## 4) Product card labeling
### 4.1 Sale label
Sale label is shown on a product if ALL/ANY of the trigger conditions apply (as listed below). :contentReference[oaicite:21]{index=21}
**Trigger conditions**
- `sale_price != null`
- `MSRP != null`
- Price list assignment meets conditions :contentReference[oaicite:22]{index=22}

### 4.2 Sold out label / Pre-order label
These labels are mentioned but not specified in detail in the provided spec excerpt. :contentReference[oaicite:23]{index=23}

---

## 5) Without Results state (Empty state)
When the user query returns no results, SRP switches to “Without results” status. :contentReference[oaicite:24]{index=24}

**Components shown**
- Trending products
- Recently viewed products :contentReference[oaicite:25]{index=25}

---

## 6) Trending Products (Without Results)
**Location**
- Product list / Without Results status. :contentReference[oaicite:26]{index=26}

### 6.1 Definition
- Trending Products = list of best-selling products in the store. :contentReference[oaicite:27]{index=27}
- Can be configured in 2 places:
  - Instant Search Widget — Without Results
  - Search Result Page — Without Results :contentReference[oaicite:28]{index=28}
- Input source can be:
  - Automatic (system-generated)
  - Manual (merchant input, or copied from the other location) :contentReference[oaicite:29]{index=29}

### 6.2 Data sources
#### Option 1 — Automatic
- Order data is crawled and analyzed monthly from the installation date. :contentReference[oaicite:30]{index=30}
- Pipeline:
  1) Get per-product order count and revenue from BigCommerce. :contentReference[oaicite:31]{index=31}
  2) Normalize order count and revenue to [0, 1]. :contentReference[oaicite:32]{index=32}
  3) Compute `trending_point`:
     - `trending_point = order_num_norm * 0.7 + revenue_norm * 0.3` :contentReference[oaicite:33]{index=33}
  4) Select top 30 products by trending_point for the Trending list. :contentReference[oaicite:34]{index=34}

#### Option 2 — Manual
- Merchant manually selects products; list remains unchanged until merchant updates it. :contentReference[oaicite:35]{index=35}
- Two manual input methods:
  1) Add products one by one
  2) Copy from Instant Search Widget — Without Results list :contentReference[oaicite:36]{index=36}
- If the source list is not set up, the copy option is unavailable. :contentReference[oaicite:37]{index=37}

### 6.3 Display rules
- Order: trending_point high → low :contentReference[oaicite:38]{index=38}
- Max quantity: 10 products :contentReference[oaicite:39]{index=39}
- Data fetching/display:
  - Determine the product count by the rule above
  - Display products with highest trending_point that are **in stock** :contentReference[oaicite:40]{index=40}

---

## 7) Recently Viewed Products (Without Results)
**Location**
- Product list / Without Results status. :contentReference[oaicite:41]{index=41}

### 7.1 Definition
- Recently viewed = products the shopper has viewed within a prior time window. :contentReference[oaicite:42]{index=42}
- This feature is integrated from **Native Recommender**. :contentReference[oaicite:43]{index=43}

### 7.2 Setup & behavior
System checks whether the merchant installed Native Recommender. :contentReference[oaicite:44]{index=44}

- Case 1: Not installed
  - Toggle is OFF
  - Show CTA to guide installation of Native Recommender :contentReference[oaicite:45]{index=45}

- Case 2: Installed
  - Native Search receives the script file from Native Recommender’s Recently Viewed flow and displays it :contentReference[oaicite:46]{index=46}

---

## 8) Acceptance checklist (implementation-ready)
- SRP renders 4 major parts: Header, Filter, Product, Category & Blog. :contentReference[oaicite:47]{index=47}
- Sorting dropdown includes all “Relevance Setting” options listed in spec. :contentReference[oaicite:48]{index=48}
- Show more / Infinite scroll load size follows `5 * products_per_row`. :contentReference[oaicite:49]{index=49}
- Sale label displays only when trigger conditions are met. :contentReference[oaicite:50]{index=50}
- Without results state shows Trending products + Recently viewed products. :contentReference[oaicite:51]{index=51}
- Trending products:
  - Supports Auto + Manual sources
  - Ranks by trending_point desc, max 10, in-stock only :contentReference[oaicite:52]{index=52}
- Recently viewed:
  - Depends on Native Recommender install status (toggle/CTA/script). :contentReference[oaicite:53]{index=53}

---

## 9) Open questions to confirm
1) Date sorting: what field/time source is used (created_at, published_at, updated_at)? :contentReference[oaicite:54]{index=54}  
2) Review sorting: which review metric (avg rating, rating count, Wilson score)? :contentReference[oaicite:55]{index=55}  
3) Sold out / Pre-order label rules (conditions + priority vs Sale label). :contentReference[oaicite:56]{index=56}  
4) Category/Blog paging + sorting: share same rules as Product or have separate logic? (design-dependent)
