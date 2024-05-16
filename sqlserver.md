# docker command
```sh
docker pull mcr.microsoft.com/mssql/server
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=yourStrong(!)Password" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2022-latest
```
# Collation 변경
```sql
SELECT name, description
FROM sys.fn_helpcollations()
ORDER BY name;
```
```sql
ALTER TABLE YourTableName
ALTER COLUMN YourColumnName VARCHAR(50) COLLATE NewCollationName;
```
