---
tags:
  - PostgreSQL
---

## Starting a sequence at MAX(column) + 1

```sql
SELECT SETVAL('public."table_Id_seq"', COALESCE(MAX("Id"), 1)) FROM public."table";
```