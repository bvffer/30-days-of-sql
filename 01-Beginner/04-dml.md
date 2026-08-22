---
day: <% tp.file.title %>
topic: Data Manipulation Language (DML)
section: 01-Beginner
tags: [sql, 30-days-sql, beginner, dml]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Data Manipulation Language (DML)

## Today's Focus
- Add records with INSERT
- Change records with UPDATE
- Remove records with DELETE

## Syntax Reference

```sql
-- INSERT: single row
INSERT INTO schema.table_name (col1, col2)
VALUES ('a', 'b');

-- INSERT: multiple rows
INSERT INTO schema.table_name (col1, col2)
VALUES ('a', 'b'), ('c', 'd');

-- INSERT from another query
INSERT INTO target_table (col1, col2)
SELECT colA, colB FROM source_table WHERE ...;

-- UPDATE: always with a WHERE
UPDATE t
SET t.col1 = 'new value'
FROM schema.table_name AS t
WHERE t.id = 5;

-- DELETE: always with a WHERE
DELETE FROM schema.table_name WHERE id = 5;
```

## DELETE vs TRUNCATE

| Aspect | DELETE | TRUNCATE |
| ------ | ------ | -------- |
| WHERE clause | Yes | No |
| Removes all rows? | One by one | Deallocates pages |
| Resets identity | No | Yes |
| Fires triggers | Yes | No |
| Logged | Fully | Minimally |

> [!warning] Safety routine before UPDATE or DELETE
> - Run the same WHERE as a SELECT first and inspect rows
> - Wrap in a transaction, verify, then COMMIT or ROLLBACK

```sql
BEGIN TRAN;
    SELECT * FROM schema.table_name WHERE id = 5;
    DELETE FROM schema.table_name WHERE id = 5;
-- check results, then:
COMMIT;   -- or ROLLBACK;
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

> [!warning] DML traps
> - Missing WHERE affects every row in the table
> - UPDATE joins can multiply rows if join keys are not unique
> - INSERT column list omitted = fragile when table structure changes

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[03-ddl]]
- Next: [[05-filtering-data]]
- Related notes: [[03-ddl]] | [[20-stored-procedures-triggers]]
