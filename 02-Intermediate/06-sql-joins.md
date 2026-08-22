---
day: <% tp.file.title %>
topic: SQL Joins
section: 02-Intermediate
tags: [sql, 30-days-sql, intermediate, joins]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - SQL Joins

## Today's Focus
- Understand every join type and when to use it
- Practice multi-table joins
- Be able to explain joins in an interview

## Join Types Comparison

| Join Type | Returns | Unmatched rows from left | Unmatched rows from right | Typical Use |
| --------- | ------- | ------------------------ | ------------------------- | ----------- |
| INNER | Only matches | Discarded | Discarded | Default when both sides required |
| LEFT | All left + matches | Kept (NULLs) | Discarded | Keep all primary records |
| RIGHT | All right + matches | Discarded | Kept (NULLs) | Same as LEFT, mirrored |
| FULL | All from both sides | Kept (NULLs) | Kept (NULLs) | Reconciliation |
| LEFT ANTI | Left rows with NO match | Kept only | - | Find orphans / missing |
| RIGHT ANTI | Right rows with NO match | - | Kept only | New keys in source |
| FULL ANTI | Rows with no match on either side | Kept | Kept | Delta between two sources |
| CROSS | Cartesian product (every x every) | - | - | Generate combinations |

> [!note]
> SQL Server has no ANTI JOIN keyword - write it as `LEFT JOIN ... WHERE right.key IS NULL`.

## Syntax Reference

```sql
SELECT c.customer_id, o.order_id
FROM sales.customers AS c
INNER JOIN sales.orders AS o
    ON c.customer_id = o.customer_id;

-- LEFT ANTI JOIN pattern in SQL Server
SELECT c.customer_id
FROM sales.customers AS c
LEFT JOIN sales.orders AS o
    ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;
```

## Multi-Table Joins

```sql
-- Chain joins one at a time; check row counts after each join
FROM a
JOIN b ON a.k = b.k
JOIN c ON b.k2 = c.k2
LEFT JOIN d ON c.k3 = d.k3;
```

Notes:
- 

## How to Choose the Correct Join

1. Do I need rows without a match? -> OUTER, otherwise INNER
2. Do I need unmatched rows ONLY? -> ANTI pattern
3. Do I need combinations? -> CROSS

My decision notes:
- 

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** Match orders to their customers.

```sql
-- Your solution
```

**Task:** Multi-table join across three tables.

```sql
-- Your solution
```

## Gotchas

> [!warning] Join traps
> - Non-unique join key on the "one" side duplicates rows silently
> - NULLs never match each other in joins (but do match in set operators)
> - Filter placement matters: WHERE vs ON changes behavior for outer joins
> - Always compare row counts before/after joining to spot explosion

## Interview Question: Explain Your Joins

> [!question] Walk through which joins you used in your project and why.
> Answer in your own words:
> - 

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[05-filtering-data]]
- Next: [[07-sql-set-operators]]
- Related notes: [[07-sql-set-operators]] | [[10-null-functions]] | [[23-performance-best-practices]]
