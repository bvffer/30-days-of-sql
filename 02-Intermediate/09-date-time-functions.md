---
day: <% tp.file.title %>
topic: Date & Time Functions
section: 02-Intermediate
tags: [sql, 30-days-sql, intermediate, date-time]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Date & Time Functions

## Today's Focus
- Extract parts of dates
- Format and cast date values
- Do date arithmetic (add, diff)
- Know which function to pick for each job

## Function Groups

### 1. Extraction

| Function | Purpose | Example |
| -------- | ------- | ------- |
| DAY / MONTH / YEAR | Integer part of a date | `YEAR(order_date)` |
| DATEPART(part, d) | Any part as integer | `DATEPART(qq, order_date)` |
| DATENAME(part, d) | Part as text | `DATENAME(month, order_date)` |
| DATETRUNC(part, d) | Truncate to boundary | `DATETRUNC(month, order_date)` |
| EOMONTH(d, add) | Last day of month | `EOMONTH(order_date)` |

### 2. Formatting & Casting

| Function | Purpose | Notes |
| -------- | ------- | ----- |
| CAST(x AS type) | Standard conversion | Fast, ANSI |
| CONVERT(type, x, style) | T-SQL conversion with styles | Style codes for dates |
| FORMAT(x, fmt, culture) | Custom display strings | Flexible but slowest |

### 3. Arithmetic & Validation

| Function | Purpose | Example |
| -------- | ------- | ------- |
| DATEADD(part, n, d) | Add interval | `DATEADD(month, -3, GETDATE())` |
| DATEDIFF(part, start, end) | Count boundaries crossed | `DATEDIFF(day, ship, order)` |
| ISDATE(x) | Is it a valid date? | Validation before casting |

## Which One Should I Use?

> [!tip] Decision guide
> - Grouping by month? -> DATETRUNC or YEAR()/MONTH()
> - Display "January"? -> DATENAME or FORMAT
> - Storing/comparing? -> keep native types, avoid FORMAT
> - Performance critical? -> CAST/CONVERT over FORMAT

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Use Case: Date Extraction

```sql
-- Your use-case solution
```

## Practice Exercise

**Task:** 

```sql
-- Your solution
```

## Gotchas

> [!warning] Date function traps
> - DATEDIFF counts boundary crossings, not elapsed time
> - FORMAT is convenient but slow - avoid in large queries
> - Implicit string-to-date conversion depends on language settings
> - DATENAME returns text - sorting it gives alphabetical order, not calendar order

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[08-string-functions]]
- Next: [[10-null-functions]]
- Related notes: [[08-string-functions]] | [[15-window-value-functions]]
