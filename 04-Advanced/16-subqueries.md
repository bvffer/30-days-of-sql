---
day: <% tp.file.title %>
topic: Subqueries
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, subqueries]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Subqueries

## Today's Focus
- Classify subqueries by result type and placement
- Use IN, ALL, ANY, EXISTS correctly
- Understand correlated subqueries

## Subquery Categories

| Dimension | Types |
| --------- | ----- |
| Result type | Scalar (one value), Multi-row (list), Table (result set) |
| Placement | SELECT, FROM, WHERE, JOIN |
| Dependency | Self-contained vs Correlated |

## Placement Cheat Sheet

| Placement | Requires | Example use |
| --------- | -------- | ----------- |
| FROM | Alias for derived table | Pre-aggregate before joining |
| SELECT | Scalar result only | Per-row lookup |
| WHERE | Scalar or list | Filter against computed values |
| JOIN | Derived table + alias | Join on aggregated data |

## Syntax Reference

```sql
-- Subquery in FROM (derived table - alias required!)
SELECT d.category, d.total
FROM (
    SELECT category, SUM(amount) AS total
    FROM orders GROUP BY category
) AS d;

-- IN operator (multi-row)
SELECT * FROM customers
WHERE country_id IN (SELECT id FROM countries WHERE region = 'EU');

-- ALL / ANY
WHERE amount > ALL (SELECT amount FROM orders WHERE year = 2023)

-- Correlated subquery + EXISTS
SELECT c.* FROM customers c
WHERE EXISTS (
    SELECT 1 FROM orders o
    WHERE o.customer_id = c.customer_id
      AND o.amount > 1000
);
```

## How the DB Executes It

Notes on execution (when does inner run? once or per-row?):
- Self-contained: 
- Correlated: 

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

> [!warning] Subquery traps
> - NOT IN with NULLs inside the subquery returns zero rows - prefer NOT EXISTS
> - Derived tables always need an alias in SQL Server
> - Correlated subqueries can execute per row - check the plan for scans
> - IN is fine for small lists; joins often scale better for large sets

## Interview Questions

> [!question] IN vs EXISTS - which one and why?
> - 

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[15-window-value-functions]]
- Next: [[17-cte]]
- Related notes: [[17-cte]] | [[05-filtering-data]] | [[06-sql-joins]]
