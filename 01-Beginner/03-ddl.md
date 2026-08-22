---
day: <% tp.file.title %>
topic: Data Definition Language (DDL)
section: 01-Beginner
tags: [sql, 30-days-sql, beginner, ddl]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Data Definition Language (DDL)

## Today's Focus
- Create objects with CREATE (tables, columns, constraints)
- Modify structure with ALTER
- Remove objects with DROP

## Syntax Reference

```sql
-- CREATE: define a new table
CREATE TABLE schema.table_name (
    column1 INT PRIMARY KEY,
    column2 VARCHAR(100) NOT NULL,
    column3 DECIMAL(10,2) DEFAULT 0,
    created_at DATETIME2 DEFAULT SYSDATETIME()
);

-- ALTER: change an existing table
ALTER TABLE table_name ADD new_column INT;
ALTER TABLE table_name ALTER COLUMN column2 VARCHAR(200);
ALTER TABLE table_name DROP COLUMN old_column;

-- DROP: remove the object entirely
DROP TABLE IF EXISTS schema.table_name;
```

## Key Concepts

| Concept | In my own words |
| ------- | --------------- |
| CREATE | |
| ALTER | |
| DROP | |
| Constraints (PK, FK, UNIQUE, CHECK, DEFAULT) | |

> [!warning] DDL is destructive and usually auto-committed
> - DROP removes data permanently - back up or script out first
> - ALTER COLUMN can fail if existing data violates the new type/size

## Practice Exercise

**Task:** Create a table, add a column to it, then drop it safely.

```sql
-- Your solution
```

## Checklist Before Writing DDL

- [ ] Naming convention followed
- [ ] Correct data types chosen (smallest that fit)
- [ ] NULL / NOT NULL decided per column
- [ ] Primary key defined

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[02-select-query]]
- Next: [[04-dml]]
- Related notes: [[19-ctas-temp-tables]] | [[21-indexes]]

