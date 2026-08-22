---
day: <% tp.file.title %>
topic: SELECT Query
section: 01-Beginner
tags: [sql, 30-days-sql, beginner, select]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - SELECT Query

## Today's Focus
- Master the building blocks of a query: SELECT, FROM, WHERE, GROUP BY, HAVING, ORDER BY
- Understand DISTINCT and TOP
- Memorize the logical execution order

## Clause Reference

| Clause | Purpose | Example |
| ------ | ------- | ------- |
| SELECT | Choose columns / expressions | `SELECT name, salary * 1.1` |
| FROM | Source table or view | `FROM employees` |
| WHERE | Filter rows (before grouping) | `WHERE salary > 5000` |
| GROUP BY | Group rows for aggregation | `GROUP BY department` |
| HAVING | Filter groups | `HAVING COUNT(*) > 5` |
| ORDER BY | Sort results | `ORDER BY salary DESC` |
| DISTINCT | Remove duplicates | `SELECT DISTINCT city` |
| TOP | Limit rows returned | `SELECT TOP 10 ...` |

## Logical Execution Order

```text
FROM        -> define source data
WHERE       -> filter individual rows
GROUP BY    -> group rows
HAVING      -> filter groups
SELECT      -> compute columns / aggregates
DISTINCT    -> remove duplicate output rows
ORDER BY    -> sort final result
TOP         -> limit final result
```

## Code Snippets

```sql
-- Annotated queries from the lectures
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Gotchas

> [!warning] Common mistakes with SELECT
> - WHERE vs HAVING confusion (rows vs groups)
> - Column aliases cannot be used inside WHERE
> - `TOP` without `ORDER BY` gives unpredictable rows
> - `TOP N WITH TIES` may return more than N rows

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[01-introduction-to-sql]]
- Next: [[03-ddl]]
- Related notes: [[05-filtering-data]] | [[12-window-functions-basics]]
