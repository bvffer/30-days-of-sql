---
day: <% tp.file.title %>
topic: Common Table Expressions (CTE)
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, cte]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Common Table Expressions (CTE)

## Today's Focus
- Write standalone, multiple, and nested CTEs
- Understand how the DB executes a CTE
- Master recursive CTEs
- Follow CTE best practices

## Syntax Reference

```sql
-- Standalone CTE
WITH sales_by_country AS (
    SELECT country_id, SUM(amount) AS total
    FROM orders
    GROUP BY country_id
)
SELECT * FROM sales_by_country;

-- Multiple CTEs
WITH cte1 AS (...),
     cte2 AS (...)
SELECT ... FROM cte1 JOIN cte2 ON ...;

-- Nested CTE (later CTE references earlier one)
WITH base AS (...),
     enriched AS (
         SELECT ..., extra_col FROM base JOIN ...
     )
SELECT * FROM enriched;

-- Recursive CTE: anchor + recursive member
WITH numbers AS (
    -- anchor
    SELECT 1 AS n
    UNION ALL
    -- recursive member (references the CTE itself)
    SELECT n + 1 FROM numbers WHERE n < 10
)
SELECT * FROM numbers;
```

## CTE Types

| Type | Description | Use for |
| ---- | ----------- | ------- |
| Standalone | One named query | Simplify a single step |
| Multiple | Several comma-separated | Break pipeline into stages |
| Nested | Later CTEs build on earlier ones | Layered transformations |
| Recursive | References itself with termination condition | Hierarchies, sequences, org charts |

## How the DB Executes a CTE

Notes (inlining vs materialization in SQL Server):
- 

## Best Practices Checklist

- [ ] Give every CTE a meaningful name describing WHAT it returns
- [ ] Comment each stage of multi-step pipelines
- [ ] Always verify recursive termination conditions to avoid infinite loops
- [ ] Remember: CTE is not a temp table - it can be re-evaluated per reference
- [ ] Prefer multiple simple CTEs over one giant unreadable query

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** Build a 3-stage CTE pipeline.

```sql
-- Your solution
```

**Task:** Recursive hierarchy walk (org chart or category tree).

```sql
-- Your solution
```

## Gotchas

> [!warning] CTE traps
> - A CTE referenced twice is executed twice unless the optimizer handles it - consider CTAS/temp tables for heavy logic
> - Missing recursion guard = infinite loop / max recursion error
> - Only the immediately following statement can use the CTE
> - OPTION (MAXRECURSION n) controls recursion depth limit in SQL Server

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[16-subqueries]]
- Next: [[18-views]]
- Related notes: [[16-subqueries]] | [[14-window-ranking-functions]] | [[18-views]] | [[19-ctas-temp-tables]]
