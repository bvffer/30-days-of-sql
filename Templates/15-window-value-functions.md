---
day: <% tp.file.title %>
topic: Window Value Functions
section: 03-Window-Functions
tags: [sql, 30-days-sql, window-functions, value-functions]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Window Value Functions

## Today's Focus
- Compare rows to neighbors with LEAD and LAG
- Use FIRST_VALUE and LAST_VALUE correctly
- Build MoM growth, retention, and time gap analyses

## Function Reference

| Function | Purpose | Notes |
| -------- | ------- | ----- |
| LEAD(col, n, default) | Value from next row(s) | NULL if beyond partition |
| LAG(col, n, default) | Value from previous row(s) | NULL at partition start |
| FIRST_VALUE(col) | First value in frame | Set full frame explicitly |
| LAST_VALUE(col) | Last value in frame | Default frame trap - see below |

## Syntax Reference

```sql
-- Previous vs current month revenue
LAG(revenue) OVER (PARTITION BY store_id ORDER BY month)      AS prev_month,
LEAD(revenue) OVER (PARTITION BY store_id ORDER BY month)     AS next_month,

-- MoM growth percent
100.0 * (revenue - LAG(revenue) OVER (
            PARTITION BY store_id ORDER BY month))
        / LAG(revenue) OVER (PARTITION BY store_id ORDER BY month) AS mom_pct,

-- Correct full-frame usage for FIRST/LAST VALUE
FIRST_VALUE(revenue) OVER (
    PARTITION BY store_id ORDER BY month
    ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING) AS first_month,
LAST_VALUE(revenue) OVER (
    PARTITION BY store_id ORDER BY month
    ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING) AS last_month
```

## Use Case Recipes

**Month-over-Month analysis:**
- Business question:
```sql
-- Your solution
```

**Customer retention (next purchase within X days?):**
- Business question:
```sql
-- Your solution
```

**Time gap between events (DATEDIFF over LAG):**
- Business question:
```sql
-- Your solution
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

> [!warning] Value function traps
> - LAST_VALUE without `ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING` returns CURRENT ROW - classic bug
> - Division by zero/NULL in MoM math - guard with NULLIF
> - LAG/LEAD offsets cross partition boundaries never happen - they stay within partitions
> - Sorting by non-unique columns makes "previous row" ambiguous - add tiebreakers

## Interview Questions

> [!question] How would you compute month-over-month growth in pure SQL?
> - 

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[14-window-ranking-functions]]
- Next: [[16-subqueries]]
- Related notes: [[12-window-functions-basics]] | [[09-date-time-functions]] | [[27-sql-advanced-data-analytics-project]]
