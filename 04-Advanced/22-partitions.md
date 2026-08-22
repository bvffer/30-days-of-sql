---
day: <% tp.file.title %>
topic: Partitions
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, partitions]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Partitions

## Today's Focus
- Understand what table partitioning is and why it matters
- Learn the full process: partition function -> scheme -> table
- Measure partition performance benefits

## Key Concepts

| Concept | In my own words |
| ------- | --------------- |
| Partition function | |
| Partition scheme | |
| Partitioned table | |
| Partition elimination | |

## The Process

```sql
-- 1. Partition function: define boundaries (RANGE RIGHT = boundary belongs to next partition)
CREATE PARTITION FUNCTION pf_year (DATE)
AS RANGE RIGHT FOR VALUES ('2022-01-01', '2023-01-01', '2024-01-01');

-- 2. Partition scheme: map partitions to filegroups
CREATE PARTITION SCHEME ps_year
AS PARTITION pf_year ALL TO ([PRIMARY]);

-- 3. Create table on the scheme
CREATE TABLE sales.orders (
    order_id INT,
    order_date DATE NOT NULL,
    amount DECIMAL(10,2)
) ON ps_year (order_date);

-- Inspect distribution
SELECT $PARTITION.pf_year(order_date) AS part, COUNT(*) AS rows
FROM sales.orders GROUP BY $PARTITION.pf_year(order_date);
```

## When Partitions Help

- Large tables with a natural range key (dates)
- Sliding window loads/drops (SWITCH in/out instead of DELETE)
- Queries filtered by the partition key (elimination)

When they do NOT help:
- 

## Performance Notes

Test results / observations from the lectures:
| Query | Without partitioning | With partitioning |
| ----- | -------------------- | ------------------- |
|       |                      |                     |

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** Partition a table by year and verify elimination with the execution plan.

```sql
-- Your solution
```

## Gotchas

> [!warning] Partition traps
> - Partition key must be part of any unique index/primary key
> - No WHERE filter on the partition key = no elimination = no benefit
> - RANGE LEFT vs RIGHT changes where boundary values land
> - Too many tiny partitions add overhead - keep count sensible

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[21-indexes]]
- Next: [[23-performance-best-practices]]
- Related notes: [[21-indexes]] | [[25-sql-data-warehouse-project]]
