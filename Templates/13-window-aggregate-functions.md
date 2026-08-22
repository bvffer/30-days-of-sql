---
day: <% tp.file.title %>
topic: Window Aggregate Functions
section: 03-Window-Functions
tags: [sql, 30-days-sql, window-functions, aggregates]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Window Aggregate Functions

## Today's Focus
- Use COUNT, SUM, AVG, MIN, MAX as window functions
- Build rolling and running totals with frames
- Build moving averages

## Syntax Reference

```sql
-- Partition-wide aggregate repeated on every row (no ORDER BY)
SUM(amount) OVER (PARTITION BY customer_id)

-- Running total (frame starts at first row)
SUM(amount) OVER (
    PARTITION BY customer_id
    ORDER BY order_date
    ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
)

-- Moving average of current + previous 2 rows
AVG(amount) OVER (
    PARTITION BY customer_id
    ORDER BY order_date
    ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
)

-- Percent of group total
amount * 100.0 / SUM(amount) OVER (PARTITION BY category)
```

## Patterns Cheat Sheet

| Pattern | Frame |
| ------- | ----- |
| Group total on every row | No ORDER BY |
| Running total | UNBOUNDED PRECEDING -> CURRENT ROW |
| Rolling N-period | N-1 PRECEDING -> CURRENT ROW |
| Percent of total | value / SUM() OVER (partition) |

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Use Case: Rolling & Running Total

**Business question:** 
```sql
-- Your solution
```

## Use Case: Moving Average

**Business question:** 
```sql
-- Your solution
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Gotchas

> [!warning] Aggregate window traps
> - Default frame with ORDER BY is RANGE - peers get the same running value; use ROWS for exact rows
> - COUNT(col) skips NULLs while COUNT(*) does not - same as GROUP BY rules
> - AVG over integers does integer division in some engines - cast to decimal
> - Frames are expensive on wide partitions - test performance

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[12-window-functions-basics]]
- Next: [[14-window-ranking-functions]]
- Related notes: [[12-window-functions-basics]] | [[14-window-ranking-functions]] | [[27-sql-advanced-data-analytics-project]]
