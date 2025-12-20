---
tags:
  - database
  - sql
  - postgres
  - reference
  - cheatsheet
---

# PostgreSQL

> [!INFO]
> **PostgreSQL** is an advanced, open-source relational database system.  
> This note summarizes essential SQL commands, psql meta-commands, and best practices.

**Related Notes:**
- [[Docker]] – Running Postgres in containers.
- [[AWS]] – RDS connection info.

---

## 🧱 Basic Commands

| Action | Command |
|--------|----------|
| Connect to a database | `psql -h <host> -U <user> -d <db>` |
| List databases | `\l` |
| Switch database | `\c <dbname>` |
| List tables | `\dt` |
| Describe a table | `\d <table>` |
| Show current user | `\du` |
| Quit psql | `\q` |
| Clear screen | `Ctrl + L` or `\! clear` |

---

## 📊 Common SQL Queries

### SELECT
```sql
SELECT * FROM public.jobs;
SELECT name, status FROM public.jobs WHERE progress < 100;
SELECT COUNT(*) FROM public.taskdetails WHERE status = 'Completed';
```

### INSERT
```sql
INSERT INTO public.jobs (name, filename, language, status)
VALUES ('Job 1', 'diagram.png', 'English', 'Pending');
```

### UPDATE
```sql
UPDATE public.jobs
SET progress = 100, status = 'Completed'
WHERE id = 5;
```

### DELETE
```sql
DELETE FROM public.jobs WHERE id = 5;
```

---

## ⚙️ Schema & Structure

| Command | Description |
|----------|--------------|
| `\d` | List tables, views, sequences |
| `\d <table>` | Show columns, types, constraints |
| `\dt` | Show all tables |
| `\dv` | Show all views |
| `\di` | Show all indexes |

---

## 🧮 Joins

```sql
-- INNER JOIN
SELECT j.id, j.name, t.status
FROM public.jobs j
JOIN public.taskdetails t ON j.taskdetailid = t.id;

-- LEFT JOIN
SELECT j.id, t.status
FROM public.jobs j
LEFT JOIN public.taskdetails t ON j.taskdetailid = t.id;
```

---

## 🧰 Functions & Aggregates

```sql
SELECT COUNT(*) FROM jobs;
SELECT AVG(progress) FROM jobs;
SELECT MAX(createddate) FROM jobs;
SELECT DISTINCT(language) FROM jobs;
```

---

## 🚀 Performance Tips

- Use `EXPLAIN ANALYZE` to inspect query performance:
  ```sql
  EXPLAIN ANALYZE SELECT * FROM jobs WHERE status='Completed';
  ```
- Add indexes to frequently queried columns:
  ```sql
  CREATE INDEX idx_jobs_status ON public.jobs(status);
  ```

---

## 🧩 Maintenance

| Action                  | Command                                                                          |
| ----------------------- | -------------------------------------------------------------------------------- |
| Show active connections | `SELECT * FROM pg_stat_activity;`                                                |



---

## 🧠 psql Meta-commands Quicklist

| Command | Description |
|----------|-------------|
| `\?` | Help on psql commands |
| `\h` | Help on SQL syntax |
| `\conninfo` | Show connection info |
| `\timing` | Toggle query execution time |
| `\watch 2` | Re-run the last query every 2 seconds |

---

## 💡 Useful Patterns

### Select top N
```sql
SELECT * FROM jobs ORDER BY createddate DESC LIMIT 5;
```

### Case / Conditional
```sql
SELECT name,
       CASE WHEN progress = 100 THEN 'Done' ELSE 'In Progress' END AS progress_state
FROM jobs;
```

### Date filtering
```sql
SELECT * FROM jobs WHERE createddate >= NOW() - INTERVAL '7 days';
```

---

## 🧰 Tools Integration

- **VS Code PostgreSQL Extension:** Run queries via `Ctrl+Shift+E` inside `.sql` files.
- **DBeaver / TablePlus / Beekeeper Studio:** Visual explorers for schema and ERD generation.
- **pgAdmin:** Official PostgreSQL GUI; ideal for local management.

---

## 🔐 Connection IPID

### Local Connection
1. Password: 
```bash
Select-String -Path .\docker-compose.yml -Pattern 'POSTGRES_PASSWORD'
```
2. Vs Code:

![[PostgresSQL LOCAL.png]]
Terminal:
```bash
psql -h 127.0.0.1 -p 5432 -U postgres -d ipidDB
```

### Remote SSH
1. Password: 
```bash
kubectl -n ipid get secret postgresql -o jsonpath='{.data.postgres-password}' | base64 --decode && echo
```
2. Kubernetes Port-Forwarding on SSH Machine
```bash
kubectl -n ipid port-forward svc/postgresql 5432:5432
```
3. Vs Code: 

![[PostgresSQL SSH Main.png]]
![[PostgresSQL SSH SSH Tunnel.png]]

---

## 🧩 Reference

- [PostgreSQL Docs](https://www.postgresql.org/docs/)
- [psql Cheat Sheet (Postgres Wiki)](https://wiki.postgresql.org/wiki/Psql_cheat_sheet)
- [SQL Style Guide](https://www.sqlstyle.guide/)
