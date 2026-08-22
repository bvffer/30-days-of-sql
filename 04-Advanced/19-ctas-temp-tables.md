---
day: <% tp.file.title %>
topic: CTAS & TEMP Tables
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, ctas, temp-tables]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - CTAS & TEMP Tables

## Today's Focus
- Materialize intermediate results with CTAS
- Understand temp table syntax and lifecycle
- Compare all methods: view vs CTE vs CTAS vs temp table

## Syntax Reference

```sql
-- CTAS: Create Table As Select (materialized snapshot)
DROP TABLE IF EXISTS schema.new_table;
SELECT col_a, SUM(col_b) AS total
INTO schema.new_table          -- SQL Server style CTAS
FROM source_table
GROUP BY col_a;

-- TEMP tables (# local = session-scoped, ## global)
CREATE TABLE #staging (
    id INT,
    name VARCHAR(100)
);

INSERT INTO #staging (id, name)
SELECT id, name FROM source WHERE load_date = '2024-01-01';

SELECT * FROM #staging;
DROP TABLE IF EXISTS #staging;   -- cleanup when done early
```

## Method Comparison

| Aspect | View | CTE | Temp Table | CTAS Table |
| ------ | ---- | --- | ---------- | ---------- |
| Stores data | No | No | TempDB | Yes |
| Lifetime | Permanent | Single statement | Session | Until dropped |
| Indexable | Limited | No | Yes | Yes |
| Statistics | No | No | Yes | Yes |
| Reuse across statements | Yes | No | Yes | Yes |
| Best for | Logic sharing | Readability | Heavy multi-step processing | Snapshots, warehouse layers |

> [!tip] My opinion on temp tables
> Great for heavy intermediate results that are reused several times - they get statistics so the optimizer makes better plans. Avoid them just for readability; use CTEs there.

## When to Choose What

| Situation | Choice |
| --------- | ------ |
| Reusable business definition | View |
| Make a complex query readable | CTE |
| Multi-step ETL with reuse + stats | Temp table |
| Persist results between loads / snapshots | CTAS table |

## How the DB Executes Them

Notes:
- CTAS: 
- Temp tables: 

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** Optimize a slow query by materializing an expensive subquery.

```sql
-- Before (slow):
```

```sql
-- After (temp table / CTAS):
```

## Gotchas

> [!warning] Materialization traps
> - SELECT INTO inherits NULLability from source - check resulting schema
> - Forgetting DROP leads to clutter and rerun failures - use IF EXISTS guards
> - Temp tables in stored procedures need care with recompilation
> - ## global temp tables are visible to ALL sessions - usually avoid

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[18-views]]
- Next: [[20-stored-procedures-triggers]]
- Related notes: [[18-views]] | [[17-cte]] | [[21-indexes]] | [[25-sql-data-warehouse-project]]
