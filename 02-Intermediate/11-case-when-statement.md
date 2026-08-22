---
day: <% tp.file.title %>
topic: CASE WHEN Statement
section: 02-Intermediate
tags: [sql, 30-days-sql, intermediate, case-when]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - CASE WHEN Statement

## Today's Focus
- Write simple and searched CASE expressions
- Apply CASE to categorize data, map values, and handle NULLs
- Learn the evaluation rules

## Two Forms of CASE

```sql
-- Searched CASE (most flexible - use this by default)
CASE
    WHEN salary >= 100000 THEN 'High'
    WHEN salary >= 50000  THEN 'Medium'
    ELSE 'Low'
END

-- Simple CASE (equality against one expression)
CASE status
    WHEN 'A' THEN 'Active'
    WHEN 'I' THEN 'Inactive'
    ELSE 'Unknown'
END
```

## Rules

> [!note] How CASE evaluates
> - Conditions checked top to bottom; first TRUE wins, rest skipped
> - No ELSE and no match -> returns NULL
> - All THEN/ELSE branches must return compatible types
> - CASE is an expression, so it works anywhere an expression is allowed (SELECT, WHERE, ORDER BY, GROUP BY)

## Use Case Recipes

**Categorizing data (buckets):**
```sql
-- Your solution
```

**Mapping values (codes to labels):**
```sql
-- Your solution
```

**Handling NULLs in output:**
```sql
-- Your solution
```

**Conditional aggregation (pivot trick):**
```sql
SUM(CASE WHEN country = 'DE' THEN amount END) AS de_revenue,
SUM(CASE WHEN country = 'FR' THEN amount END) AS fr_revenue
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

> [!warning] CASE traps
> - Overlapping conditions silently take the first match - order matters
> - Mixing return types (int + varchar) can cause conversion errors at runtime
> - CASE in WHERE is often a smell - prefer direct predicates for readability/performance
> - Aggregating with CASE: remember aggregates ignore NULLs returned by unmatched branches

## Interview Questions

> [!question] Difference between simple and searched CASE? What does CASE return without ELSE?
> - 

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[10-null-functions]]
- Next: [[12-window-functions-basics]]
- Related notes: [[10-null-functions]] | [[13-window-aggregate-functions]] | [[26-exploratory-data-analysis-project]]

