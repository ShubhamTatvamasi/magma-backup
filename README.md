# magma-backup

connect to magma database:
```bash
kubectl exec -it -n orc8r postgresql-postgresql-0 -- bash -c 'PGPASSWORD=postgres \
  psql -U postgres -d magma'
```

### Backup

backup magma database:
```bash
kubectl exec -it -n orc8r postgresql-postgresql-0 -- bash -c 'PGPASSWORD=postgres \
  pg_dump -U postgres magma' > magma-orc8r-backup.sql
```

### Restore:

create magma database:
```bash
kubectl exec -it -n orc8r postgresql-postgresql-0 -- bash -c 'PGPASSWORD=postgres \
  psql -U postgres -c "CREATE DATABASE magma WITH OWNER postgres;"'
```

restore magma database:
```bash
kubectl exec -it -n orc8r postgresql-postgresql-0 -- bash -c 'PGPASSWORD=postgres \
  psql -U postgres -d magma' < magma-orc8r-backup.sql
```
