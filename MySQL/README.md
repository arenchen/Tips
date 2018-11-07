# MySQL Tips
## Allow root remote access
```sql
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '[root password]' WITH GRANT OPTION;
```

## MySQL Backup & Restore
```shell
# Backup
mysqldump --user=root -p [Db Name] > backup.sql

# Restore
mysql --user=root -p [Db Name] < backup.sql
```
