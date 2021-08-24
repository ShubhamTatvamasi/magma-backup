# magma-backup

connect to database:
```bash
kubectl exec -it -n orc8r postgresql-0 -- bash -c \
  'PGPASSWORD=postgres psql -U postgres -d magma'
```

backup magma orc8r database:
```bash
kubectl exec -it -n orc8r postgresql-0 -- bash -c \
  'PGPASSWORD=postgres pg_dump -U postgres magma' > magma-orc8r-backup.sql
```


