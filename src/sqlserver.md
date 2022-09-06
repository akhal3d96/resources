# SQL Server


## Common commands

List all the databases

```sql
SELECT name FROM master.dbo.sysdatabases;
```


## Kubernetes

```
kubectl run --restart=Never sqltools --image=mcr.microsoft.com/mssql-tools --command sleep 99d

kubectl exec -it sqltools -- /opt/mssql-tools/bin/sqlcmd -S <HOSTNAME> -U <USERNAME> -P <PASSWORD>
```


Notes: 
1. Add `-Q` to excute query without running into the interactive console.
2. `-P` is optional.

## AWS RDS

Create a backup to S3

```sql
exec msdb.dbo.rds_backup_database
	@source_db_name='database_name',
	@s3_arn_to_backup_to='arn:aws:s3:::bucket_name/file_name.extension',
	[@kms_master_key_arn='arn:aws:kms:region:account-id:key/key-id'],	
	[@overwrite_s3_backup_file=0|1],
	[@type='DIFFERENTIAL|FULL'],
	[@number_of_files=n];
```


Check backup task status
```sql
exec msdb.dbo.rds_task_status @task_id=<TASK_ID>;
```



## References

1. [Importing and exporting SQL Server databases using native backup and restore](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/SQLServer.Procedural.Importing.html)
