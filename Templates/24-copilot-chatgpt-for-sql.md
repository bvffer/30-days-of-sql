---
day: <% tp.file.title %>
topic: Copilot & ChatGPT for SQL
section: 04-Advanced
tags: [sql, 30-days-sql, advanced, ai-tools]
status: not-started
started: <% tp.date.now("YYYY-MM-DD") %>
completed: 
---

# <% tp.file.title %> - Copilot & ChatGPT for SQL

## Today's Focus
- Understand what ChatGPT and GitHub Copilot are and how they differ
- Learn a reusable prompt structure
- Build a personal prompt library for SQL work

## ChatGPT vs Copilot

| Aspect | ChatGPT | GitHub Copilot |
| ------ | ------- | -------------- |
| Interaction | Chat / conversation | Inline in the IDE |
| Best at | Explaining, designing, reviewing | Autocompleting while typing |
| Context | Whatever you paste | Open files / repo context |

My notes:
- 

## Prompt Structure That Works

```text
[ROLE]      You are a senior SQL Server developer.
[CONTEXT]   Table schemas, sample rows, environment (SQL Server 2022).
[TASK]      What exactly you want: generate / explain / optimize / debug.
[FORMAT]    Output style: query only, with comments, step by step.
[EXAMPLE]   Optional example of desired input/output.
```

## My Prompt Library

**Generate SQL from requirements:**
```text
Your prompt here
```

**Explain an unfamiliar query:**
```text
Your prompt here
```

**Optimize a slow query:**
```text
Your prompt here
```

**Debug an error message:**
```text
Your prompt here
```

**Translate between dialects:**
```text
Your prompt here
```

**Document code / write comments:**
```text
Your prompt here
```

**Learning prompts (practice generation):**
```text
Your prompt here
```

## Evaluation Log

| Date | Task | Tool | Prompt used | Result quality | Fix applied |
| ---- | ---- | ---- | ----------- | -------------- | ----------- |
|      |      |      |             |                |             |

## Gotchas

> [!warning] AI tool traps
> - Always verify generated SQL against your actual schema - it invents columns happily
> - Never paste sensitive/production data into prompts
> - AI output is a draft, not reviewed code
> - Dialect confusion is common (MySQL vs SQL Server syntax)

## Open Questions

- [ ] 

## Recap

> [!summary] Three things I learned today
> 1. 
> 2. 
> 3. 

## Links

- Previous: [[23-performance-best-practices]]
- Next: [[25-sql-data-warehouse-project]]
- Related notes: [[23-performance-best-practices]]
