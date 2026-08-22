---
day: <% tp.file.title %>
topic: Views
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, views]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Views

## Today's Focus
- Create, alter, and drop views
- Know when to use a view vs table vs CTE
- Apply real use cases: central logic, security, flexibility, warehouse layer

## Syntax Reference

```sql
CREATE OR ALTER VIEW schema.view_name
AS
SELECT ...
FROM ...
WHERE ...;
GO

DROP VIEW IF EXISTS schema.view_name;
```

## Views vs Tables vs CTEs

| Aspect | View | Table | CTE |
| ------ | ---- | ----- | --- |
| Stores data | No | Yes | No |
| Lives | In DB permanently | In DB permanently | One statement only |
| Can be indexed | Via indexed/materialized views | N/A | No |
| Permissions | Grantable (security) | Grantable | Follows base tables |

## Use Case Notes

**Central logic (one definition of "active customer"):**
- 

**Hide complexity (wrap multi-join logic):**
- 

**Data security (expose columns, hide PII):**
- 

**Flexibility (multi-language labels):**
- 

**Data warehouse (gold layer reporting objects):**
- 

## How the DB Executes a View

Notes (expansion / inlining behavior):
- 

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** Build a view that hides complexity for business users.

```sql
-- Your solution
```

## Gotchas

> [!warning] View traps
> - Views are NOT stored queries' results - they run against live data every time
> - SELECT * in a view breaks silently when base tables change - list columns explicitly
> - Deeply nested views are a performance and debugging nightmare - keep layers shallow
> - ORDER BY inside views is ignored unless TOP/OFFSET is used

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[17-cte]]
- Next: [[19-ctas-temp-tables]]
- Related notes: [[17-cte]] | [[19-ctas-temp-tables]] | [[25-sql-data-warehouse-project]]
