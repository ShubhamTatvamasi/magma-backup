# magma-backup

connect to magma database:
```bash
kubectl exec -it -n orc8r postgresql-0 -- bash -c \
  'PGPASSWORD=postgres psql -U postgres -d magma'
```

backup magma database:
```bash
kubectl exec -it -n orc8r postgresql-0 -- bash -c \
  'PGPASSWORD=postgres pg_dump -U postgres magma' > magma-orc8r-backup.sql
```


