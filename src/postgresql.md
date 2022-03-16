# PostgreSQL

You can use `PGPASSWORD` variable to pass the password to your database.

## Backup and Restoration

### Backup

```
pg_dump -h DB_HOST -U DB_USER DB_NAME | gzip -9 > DB_BACKUP_NAME_$(date +%F).sql.gz
```

### Restore

```
gunzip -c DB_BACKUP_NAME.sql.gz | psql -h DB_HOST -U DB_USER DB_NAME
```