---
day: <% tp.file.title %>
topic: NULL Functions
section: 02-Intermediate
tags: [sql, 30-days-sql, intermediate, null-handling]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - NULL Functions

## Today's Focus
- Understand what NULL really means (unknown, not zero)
- Replace NULLs with COALESCE / ISNULL
- Predict NULL behavior in aggregation, math, joins, sorting

## COALESCE vs ISNULL

| Aspect | COALESCE | ISNULL |
| ------ | -------- | ------ |
| Standard | ANSI SQL | T-SQL only |
| Arguments | Two or more | Exactly two |
| Return type | Highest precedence of args | Type of FIRST argument |
| Evaluation | Left to right, stops at first non-null | Always evaluates both |

## Other NULL Tools

```sql
-- NULLIF: return NULL when two values are equal (great for div-by-zero)
a / NULLIF(b, 0)

-- Explicit checks
WHERE col IS NULL
WHERE col IS NOT NULL
```

## NULL Behavior Cheat Sheet

| Context | Behavior |
| ------- | -------- |
| Aggregates (SUM, AVG, MIN, MAX) | Ignore NULLs entirely |
| COUNT(*) vs COUNT(col) | COUNT(*) counts all rows; COUNT(col) skips NULLs |
| Math with NULL | Result is NULL |
| Joins on key | NULL keys never match each other |
| ORDER BY (SQL Server ASC) | NULLs sort first ascending, last descending |
| Comparisons (= <> >) | Return UNKNOWN, filtered out by WHERE |

## NULL vs Empty vs Blank

| Value | LEN() | Meaning |
| ----- | ----- | ------- |
| NULL | NULL | Unknown / missing |
| '' | 0 | Known empty string |
| ' ' | 1 | Blank space(s) |

My data policy notes (how I treat each):
- 

## Handling NULLs in Practice

**In aggregation:**
```sql
-- Your snippet
```

**In joins:**
```sql
-- Your snippet (e.g. COALESCE(key, -1))
```

**In sorting and output:**
```sql
-- Your snippet
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Gotchas

> [!warning] NULL traps
> - `= NULL` is always UNKNOWN - must use IS NULL
> - NOT IN with a NULL in the list returns zero rows
> - ISNULL forces its type from the first argument - can silently truncate
> - AVG ignores NULLs - decide if that matches your business meaning

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[09-date-time-functions]]
- Next: [[11-case-when-statement]]
- Related notes: [[06-sql-joins]] | [[11-case-when-statement]]
