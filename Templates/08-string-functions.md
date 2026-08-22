---
day: <% tp.file.title %>
topic: String Functions
section: 02-Intermediate
tags: [sql, 30-days-sql, intermediate, string-functions]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - String Functions

## Today's Focus
- Clean and transform text data
- Extract parts of strings
- Combine functions into real transformations

## Function Reference

| Function | Purpose | Example |
| -------- | ------- | ------- |
| CONCAT(a, b) | Join values | `CONCAT(first, ' ', last)` |
| UPPER / LOWER | Change case | `UPPER(city)` |
| TRIM / LTRIM / RTRIM | Strip spaces | `TRIM(name)` |
| REPLACE(s, find, new) | Substitute text | `REPLACE(phone, '-', '')` |
| LEN(s) | Character count | `LEN(name)` |
| LEFT / RIGHT | Take n chars from edge | `LEFT(code, 3)` |
| SUBSTRING(s, start, len) | Slice text | `SUBSTRING(email, 1, 5)` |

## Number Functions

| Function | Purpose |
| -------- | ------- |
| ROUND(x, n) | Round to n decimals |
| CEILING / FLOOR | Round up / down to integer |
| ABS | Absolute value |
| POWER / SQUARE / SQRT | Exponents and roots |

## Code Snippets

```sql
-- Queries I ran in the lectures
SELECT CONCAT(UPPER(LEFT(firstname,1)), '.', LOWER(lastname)) AS display_name
FROM customers;
```

## Transformation Recipes I Built

**Clean whitespace + standardize case:**
```sql
-- Your recipe
```

**Extract domain from email:**
```sql
-- Your recipe
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Gotchas

> [!warning] String function traps
> - LEN ignores trailing spaces; DATALENGTH counts bytes including them
> - SUBSTRING is 1-based, not 0-based
> - CONCAT handles NULL gracefully (converts to empty), + operator does not
> - Nested functions read inside-out - break long chains into steps

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[07-sql-set-operators]]
- Next: [[09-date-time-functions]]
- Related notes: [[09-date-time-functions]] | [[10-null-functions]] | [[11-case-when-statement]]
