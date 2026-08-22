---
day: <% tp.file.title %>
topic: Filtering Data
section: 01-Beginner
tags: [sql, 30-days-sql, beginner, filtering]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Filtering Data

## Today's Focus
- Use comparison operators correctly
- Combine conditions with AND, OR, NOT
- Filter ranges and lists with BETWEEN and IN
- Match patterns with LIKE

## Operator Reference

| Operator | Meaning | Example |
| -------- | ------- | ------- |
| = <> != > >= < <= | Comparison | `salary >= 5000` |
| AND / OR / NOT | Logical combine | `a AND b OR c` |
| BETWEEN | Inclusive range | `BETWEEN 100 AND 200` |
| IN | List membership | `IN ('DE', 'FR')` |
| LIKE | Pattern match | `LIKE 'A%'` |
| IS NULL / IS NOT NULL | Null check | `col IS NULL` |

## LIKE Wildcards

| Wildcard | Matches | Example matches |
| -------- | ------- | --------------- |
| `%` | Zero or more characters | `'A%'`: Apple, Audi |
| `_` | Exactly one character | `'_r%'`: Art |
| `[ ]` | Any char in set/range | `'[AB]%'`: Apple, Banana |
| `[^ ]` | Any char not in set | `'[^A]%'`: not starting with A |

## Operator Precedence

```text
NOT  ->  evaluated first
AND  ->  evaluated second
OR   ->  evaluated last
Use parentheses to make intent explicit.
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

> [!warning] Filtering traps
> - Comparisons with NULL are UNKNOWN, never TRUE - use IS NULL
> - BETWEEN is inclusive on both ends
> - LIKE is case-insensitive in SQL Server default collation
> - NOT IN returns nothing if the subquery contains NULL values

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[04-dml]]
- Next: [[06-sql-joins]]
- Related notes: [[02-select-query]] | [[16-subqueries]]
