---
day: <% tp.file.title %>
topic: SQL Set Operators
section: 02-Intermediate
tags: [sql, 30-days-sql, intermediate, set-operators]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - SQL Set Operators

## Today's Focus
- Learn the rules all set operators share
- Master UNION, UNION ALL, EXCEPT, INTERSECT
- Know when to use which (combine info, delta detection)

## Operator Comparison

| Operator | Returns | Duplicates | Notes |
| -------- | ------- | ---------- | ----- |
| UNION | Rows from both queries | Removed | Sorts + dedupes = slower |
| UNION ALL | Rows from both queries | Kept | Fastest, default choice when dupes are fine |
| EXCEPT | Rows in query 1 but not query 2 | Removed | Delta detection |
| INTERSECT | Rows present in both queries | Removed | Common records |

## Rules for Combining Result Sets

- Same number of columns in every SELECT
- Column order must align
- Data types must be compatible (implicit conversion may bite)
- Output column names come from the FIRST SELECT
- ORDER BY is allowed only at the end, applies to the combined result

## Syntax Reference

```sql
SELECT col_a, col_b FROM table1
UNION ALL
SELECT col_c, col_d FROM table2;

-- Delta detection: rows only in the new snapshot
SELECT key_col FROM new_snapshot
EXCEPT
SELECT key_col FROM old_snapshot;
```

## Use Case Notes

**Combine information (e.g. customers who bought OR subscribed):**
- 

**Delta detection (what changed between two loads):**
- 

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

> [!warning] Set operator traps
> - UNION hides duplicates silently - ask if that is intended
> - INTERSECT/EXCEPT compare entire rows, not just keys
> - NULLs are treated as equal by set operators (unlike joins)
> - Performance: prefer UNION ALL + explicit dedupe when possible

## Interview Questions

> [!question] Explain UNION vs UNION ALL. When is EXCEPT useful?
> - 

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[06-sql-joins]]
- Next: [[08-string-functions]]
- Related notes: [[06-sql-joins]] | [[10-null-functions]]
