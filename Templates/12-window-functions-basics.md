---
day: <% tp.file.title %>
topic: Window Functions Basics
section: 03-Window-Functions
tags: [sql, 30-days-sql, window-functions]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Window Functions Basics

## Today's Focus
- Understand what a "window" is
- Learn the OVER clause anatomy: PARTITION BY, ORDER BY, frame
- Know how windows differ from GROUP BY

## Window Function vs GROUP BY

| Aspect | GROUP BY | Window Function |
| ------ | -------- | --------------- |
| Rows in output | One per group | Every row kept |
| Detail + aggregate together? | No | Yes |
| Typical use | Summaries / reports | Analytics over related rows |

## Syntax Anatomy

```sql
FUNCTION_NAME (arguments) OVER (
    [PARTITION BY col]      -- splits rows into independent windows
    [ORDER BY col]          -- orders rows within each partition
    [ROWS/RANGE frame]      -- which rows feed the calculation
)
```

| Part | What it controls | Omitted means |
| ---- | ---------------- | ------------- |
| PARTITION BY | Grouping of rows into windows | Whole result set is one partition |
| ORDER BY | Order within partition; enables running calcs | No order semantics |
| Frame | Subset of partition per row | Depends on ORDER BY presence |

## Frame Clause Reference

```sql
ROWS BETWEEN <start> AND <end>
-- boundaries:
UNBOUNDED PRECEDING   -- first row of partition
n PRECEDING           -- n rows before current
CURRENT ROW
n FOLLOWING           -- n rows after current
UNBOUNDED FOLLOWING   -- last row of partition
```

> [!note] Default frames
> - With ORDER BY: RANGE BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
> - Without ORDER BY: whole partition
> - RANGE uses value-based peers, ROWS uses physical offsets - usually you want ROWS

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Rules and Gotchas

> [!warning] Window function rules
> - Cannot appear in WHERE or GROUP BY (executed later than WHERE) - wrap in CTE/subquery
> - ORDER BY inside OVER does NOT sort the final result - add outer ORDER BY
> - PARTITION BY without ORDER BY gives partition-wide aggregates on every row
> - Big partitions cost memory - watch execution plans on large data

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[11-case-when-statement]]
- Next: [[13-window-aggregate-functions]]
- Related notes: [[02-select-query]] | [[13-window-aggregate-functions]] | [[14-window-ranking-functions]] | [[15-window-value-functions]]
