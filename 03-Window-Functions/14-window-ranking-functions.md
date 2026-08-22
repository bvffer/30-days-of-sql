---
day: <% tp.file.title %>
topic: Window Ranking Functions
section: 03-Window-Functions
tags: [sql, 30-days-sql, window-functions, ranking]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Window Ranking Functions

## Today's Focus
- Compare ROW_NUMBER, RANK, DENSE_RANK
- Use NTILE for buckets and percentiles
- Apply ranking to Top-N analysis, unique IDs, duplicate detection

## Ranking Functions Comparison

| Function | Tie behavior | Sequence example (values 10,10,20) |
| -------- | ------------ | ----------------------------------- |
| ROW_NUMBER | Arbitrary but stable | 1, 2, 3 |
| RANK | Ties share rank, gaps after ties | 1, 1, 3 |
| DENSE_RANK | Ties share rank, no gaps | 1, 1, 2 |
| NTILE(n) | Buckets of near-equal size | depends on n |
| CUME_DIST | Cumulative distribution (0,1] | relative position incl. peers |
| PERCENT_RANK | (rank-1)/(rows-1), [0,1] | 0 = lowest in partition |

## Syntax Reference

```sql
ROW_NUMBER() OVER (PARTITION BY dept ORDER BY salary DESC) AS rn
RANK()       OVER (ORDER BY score DESC) AS rnk
DENSE_RANK() OVER (ORDER BY score DESC) AS drnk
NTILE(4)     OVER (ORDER BY revenue) AS quartile
```

## Standard Recipes

**Top N per group (classic):**
```sql
WITH ranked AS (
    SELECT *,
           ROW_NUMBER() OVER (PARTITION BY category ORDER BY sales DESC) AS rn
    FROM products
)
SELECT * FROM ranked WHERE rn <= 3;
```

**Detect duplicates:**
```sql
WITH d AS (
    SELECT *, ROW_NUMBER() OVER (PARTITION BY email ORDER BY id) AS rn
    FROM customers
)
DELETE FROM d WHERE rn > 1;   -- or SELECT first to review
```

**Assign unique IDs:** 
```sql
-- Your snippet
```

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Gotchas

> [!warning] Ranking traps
> - ROW_NUMBER without a fully deterministic ORDER BY can return different results per run - add a tiebreaker column
> - RANK vs DENSE_RANK gaps matter when filtering "top ranks"
> - Filtering on rank requires wrapping in CTE/subquery - cannot filter directly in WHERE
> - PERCENT_RANK is 0-based, CUME_DIST is not - do not mix them up in reports

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[13-window-aggregate-functions]]
- Next: [[15-window-value-functions]]
- Related notes: [[12-window-functions-basics]] | [[17-cte]]
