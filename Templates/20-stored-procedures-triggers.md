---
day: <% tp.file.title %>
topic: Stored Procedures & Triggers
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, stored-procedures, triggers]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Stored Procedures & Triggers

## Today's Focus
- Create and execute stored procedures with parameters
- Use variables and control flow (IF/ELSE)
- Handle errors with TRY/CATCH
- Understand triggers and audit logging

## Syntax Reference

```sql
-- Basic stored procedure with parameters
CREATE OR ALTER PROCEDURE schema.proc_name
    @country VARCHAR(50),
    @min_total DECIMAL(10,2) = 0 OUTPUT   -- default + output example
AS
BEGIN
    SET NOCOUNT ON;

    -- variable declaration
    DECLARE @row_count INT;

    -- control flow
    IF @country IS NULL
    BEGIN
        RAISERROR('Country is required', 16, 1);
        RETURN;
    END

    SELECT * FROM orders WHERE country = @country;
END;
GO

-- Execution
EXEC schema.proc_name @country = 'Germany';
```

## Error Handling Pattern

```sql
BEGIN TRY
    BEGIN TRAN;
        UPDATE ... ;
    COMMIT TRAN;
END TRY
BEGIN CATCH
    IF @@TRANCOUNT > 0 ROLLBACK TRAN;
    THROW;   -- re-raise to caller
END CATCH
```

## Styling Checklist for Procedures

- [ ] SET NOCOUNT ON at the top
- [ ] Meaningful parameter names with sensible defaults
- [ ] One responsibility per procedure
- [ ] Header comment: purpose, params, author, changes
- [ ] Consistent error handling strategy

## Triggers

```sql
CREATE OR ALTER TRIGGER trg_audit_orders
ON sales.orders
AFTER INSERT, UPDATE
AS
BEGIN
    INSERT INTO audit.orders_log (order_id, changed_at)
    SELECT order_id, SYSDATETIME() FROM inserted;
END;
```

Trigger use case notes:
- 

## Code Snippets

```sql
-- Queries I ran in the lectures
```

## Practice Exercise

**Task:** Build a procedure that takes a date range parameter and returns aggregated sales, with error handling.

```sql
-- Your solution
```

## Gotchas

> [!warning] Procedure and trigger traps
> - Triggers fire per statement, not per row - handle multi-row inserted/deleted sets
> - Hidden logic in triggers surprises future maintainers - document them
> - Nested trigger chains can cascade unexpectedly
> - RETURN values vs OUTPUT parameters - do not mix conventions

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[19-ctas-temp-tables]]
- Next: [[21-indexes]]
- Related notes: [[04-dml]] | [[25-sql-data-warehouse-project]]
