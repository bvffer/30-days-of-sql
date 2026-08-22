---
day: <% tp.file.title %>
topic: Performance Best Practices
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, performance]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Performance Best Practices

## Today's Focus
- Collect optimization tips by query area
- Learn to measure before and after tuning

## Tips by Area

### Fetching Data
> [!tip] Tips
> - Select only needed columns (no SELECT *)
> - Avoid functions on columns inside WHERE (kills sargability)

My notes:
- 

### Filtering
- 

### Joining
- 

### Aggregation
- 

### Subqueries
- 

### Table DDL
- 

### Indexing
- 

## Before / After Benchmark Log

| Date | Query | Problem | Change made | Result (time / plan) |
| ---- | ----- | ------- | ----------- | -------------------- |
|      |       |         |             |                      |

## Measurement Routine

1. Capture baseline execution plan + time
2. Apply one change at a time
3. Compare plans (scans vs seeks, spools, warnings)
4. Re-measure on realistic data volume

```sql
-- Snippets for measuring (SET STATISTICS TIME/TIO ON etc.)
```

## Practice Exercise

**Task:** Take one slow query from earlier notes and optimize it using today's tips.

```sql
-- Your solution
```

## Gotchas

> [!warning] Optimization traps
> - Optimizing without measuring is guessing
> - Micro-tips matter less than indexes, data volume, and plans
> - A fix that helps dev data can hurt production volume - test realistically
> - Hints are last resort, not first choice

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[22-partitions]]
- Next: [[24-copilot-chatgpt-for-sql]]
- Related notes: [[21-indexes]] | [[16-subqueries]] | [[06-sql-joins]]
