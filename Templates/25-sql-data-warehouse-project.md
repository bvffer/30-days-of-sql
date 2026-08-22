---
day: <% tp.file.title %>
topic: SQL Data Warehouse Project
section: 05-Projects
tags: [sql, 30-days-sql, project, data-warehouse]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - SQL Data Warehouse Project

## Today's Focus
- 

## Project Overview

**Goal:** Build a full data warehouse from source systems to gold layer.

| Item | Detail |
| ---- | ------ |
| Source systems | CRM + ERP CSV files |
| Layers | Bronze (raw) -> Silver (clean) -> Gold (business) |
| Tools | SQL Server, SSMS, Git, Notion |

## Architecture Notes

```text
Source (CSV) -> [ETL] -> Bronze: raw as-is
             -> [ETL] -> Silver: cleaned & conformed
             -> [ETL] -> Gold: star schema for analytics
```

My architecture sketch notes:
- 

## Layer Progress Tracker

### Bronze Layer

- [ ] Analyze source systems
- [ ] DDL: create tables
- [ ] Load scripts
- [ ] Stored procedure `load_bronze`
- [ ] Document the work

Key decisions:
- 

### Silver Layer

- [ ] Explore data quality issues
- [ ] DDL: create tables
- [ ] Load scripts per table
- [ ] Stored procedure `load_silver`
- [ ] Document the work

Data quality problems found and fixes:
| Table | Issue | Fix applied |
| ----- | ----- | ----------- |
|       |       |             |

### Gold Layer

- [ ] Data modeling (dimensions + facts)
- [ ] dim_customers
- [ ] dim_products
- [ ] fact_sales
- [ ] Draw the data model
- [ ] Create data catalog
- [ ] Document the work

Model design notes:
- 

## ETL Notes

| Method | What I learned |
| ------ | -------------- |
| Full load | |
| Incremental load | |
| Upsert / merge logic | |

## Project Management

- Naming conventions used:
- Git repo setup:
- Requirements recap:

## Gotchas and Lessons

> [!warning] Issues hit during build
> - 

## Recap

> [!summary] What I accomplished today on this project
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[24-copilot-chatgpt-for-sql]]
- Next: [[26-exploratory-data-analysis-project]]
- Related notes: [[19-ctas-temp-tables]] | [[20-stored-procedures-triggers]] | [[18-views]]
