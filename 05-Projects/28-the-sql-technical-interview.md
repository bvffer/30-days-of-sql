---
day: <% tp.file.title %>
topic: The SQL Technical Interview
section: 05-Projects
tags: [sql, 30-days-sql, interview, career]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - The SQL Technical Interview

## Today's Focus
- Review all course topics from an interviewer's perspective
- Practice explaining concepts out loud
- Solve classic interview questions end to end

## Answer Framework for Query Questions

```text
1. CLARIFY   - restate the problem, ask about edge cases and data volume
2. APPROACH  - say which clauses/functions you will use and why
3. WRITE     - clean, formatted SQL with meaningful aliases
4. TEST      - walk through a small example, mention NULLs/duplicates
5. OPTIMIZE  - mention indexes, execution plan considerations
```

## Topic Review Checklist

- [ ] SELECT, WHERE, GROUP BY, HAVING (explain the difference)
- [ ] Execution order of query clauses
- [ ] All join types + when to use each
- [ ] UNION vs UNION ALL vs EXCEPT vs INTERSECT
- [ ] String / date functions
- [ ] NULL handling (COALESCE vs ISNULL, NULLIF)
- [ ] CASE expressions
- [ ] Window functions vs GROUP BY
- [ ] ROW_NUMBER vs RANK vs DENSE_RANK (+ NTILE)
- [ ] LEAD/LAG for MoM and gap analysis
- [ ] Subqueries: correlated, EXISTS vs IN
- [ ] CTEs incl. recursive
- [ ] Views vs temp tables vs CTAS
- [ ] Stored procedures and error handling
- [ ] Indexes: clustered vs nonclustered, columnstore
- [ ] Partitions and performance tuning basics

## Question Bank

### Concept Questions

| Question | My answer (short) | Confidence |
| -------- | ----------------- | ---------- |
| WHERE vs HAVING? | | |
| Why is NOT IN risky with NULLs? | | |
| When do you choose a temp table over a CTE? | | |
| Clustered vs nonclustered index? | | |

### Coding Questions Solved

**Q1:** 
```sql
-- Solution with comments
```

**Q2:** 
```sql
-- Solution with comments
```

**Q3:** 
```sql
-- Solution with comments
```

## Mock Interview Notes

Date attempted: 
What went well: 
What to improve: 

## Gotchas

> [!warning] Interview traps I should remember
> - Talking silently while coding - narrate your thinking
> - Forgetting duplicates/NULL edge cases in solutions
> - Jumping to code before clarifying requirements

## Recap

> [!summary] Top 3 things to review again before any interview
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[27-sql-advanced-data-analytics-project]]
- Next: [[]]
- Related notes: [[02-select-query]] | [[06-sql-joins]] | [[12-window-functions-basics]] | [[16-subqueries]] | [[17-cte]] | [[21-indexes]]
