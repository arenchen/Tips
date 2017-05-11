# MySQL Tips
## MySQL Backup & Restore
```shell
# Backup
mysqldump --user=root -p [Db Name] > backup.sql

# Restore
mysql --user=root -p [Db Name] < backup.sql
```
