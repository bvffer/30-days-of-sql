---
day: <% tp.file.title %>
topic: Indexes
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, indexes, performance]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Indexes

## Today's Focus
- Understand heap, clustered, and nonclustered index structures
- Learn columnstore vs rowstore
- Know the index types: composite, unique, filtered
- Monitor and maintain indexes (statistics, fragmentation, plans)

## Core Structures

| Concept | In my own words |
| ------- | --------------- |
| Heap | Table with no clustered index |
| Clustered index | Physical sort order of table rows - one per table |
| Nonclustered index | Separate structure pointing back to rows - many allowed |
| Columnstore | Column-based storage, great for analytics/warehouse |
| Rowstore | Traditional row storage, great for OLTP point lookups |

## Index Types Checklist

| Type | Purpose |
| ---- | ------- |
| Composite | Multiple key columns (order matters) |
| Unique | Enforce uniqueness + speed lookups |
| Filtered (WHERE clause) | Small hot subsets, e.g. active rows |
| Columnstore | Aggregations over big fact tables |

## Creating and Choosing Indexes

```sql
-- Nonclustered composite with included columns
CREATE NONCLUSTERED INDEX IX_orders_customer_date
ON sales.orders (customer_id, order_date DESC)
INCLUDE (amount);

-- Unique
CREATE UNIQUE INDEX UX_customers_email ON sales.customers (email);

-- Filtered
CREATE INDEX IX_orders_open ON sales.orders (order_date)
WHERE status = 'open';

-- Columnstore for warehouse facts
CREATE CLUSTERED COLUMNSTORE INDEX CCI_facts ON dw.fact_sales;
```

> [!tip] Choosing the right index
> Key column order: equality predicates first, then range/sort columns. INCLUDE covers SELECT-only columns without enlarging keys.

## Monitoring and Maintenance

| Task | What I learned |
| ---- | -------------- |
| Monitor usage (sys.dm_db_index_usage_stats) | |
| Find missing indexes (DMVs + execution plans) | |
| Find duplicate/overlapping indexes | |
| Update statistics | |
| Check fragmentation / rebuild vs reorganize | |

```sql
-- Monitoring snippets I collected
```

## Execution Plans and Hints

Notes on reading plans (scans vs seeks, estimated vs actual):
- 

SQL hints notes (when to use, when to avoid):
- 

## My Indexing Strategy Summary

1. 
2. 
3. 

## Practice Exercise

**Task:** Diagnose a slow query and add a suitable index.

```sql
-- Before:
```

```sql
-- Index added:
```

```sql
-- After:
```

## Gotchas

> [!warning] Index traps
> - Every index slows INSERT/UPDATE/DELETE - balance read vs write cost
> - Leading column rule: composite index unused if first key column is not filtered
> - Missing index DMV suggestions are not gospel - review before creating
> - Stale statistics cause bad plans after large data changes

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[20-stored-procedures-triggers]]
- Next: [[22-partitions]]
- Related notes: [[22-partitions]] | [[23-performance-best-practices]] | [[19-ctas-temp-tables]]
