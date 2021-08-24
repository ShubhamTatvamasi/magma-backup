# magma-backup

connect to database:
```bash
kubectl exec -it -n orc8r postgresql-0 -- bash -c \
  'PGPASSWORD=postgres psql -U postgres -d magma'
```

