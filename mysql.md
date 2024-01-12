# Mysql Docker run with cases insensitive option
```bash
docker pull mysql
docker run -d --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -e TZ=Asia/Seoul mysql --character-set-server=utf8 --collation-server=utf8_general_ci --lower_case_table_names=1
```

# Mysql Errors
## Public Key retrieval is not allowed( since 8.0)
Add these options to the connection string
* useSSL=false&allowPublicKeyRetrieval=true

# Add data to docker mysql
```bash
docker exec -i some-mysql sh -c 'exec mysql -uroot -p"$MYSQL_ROOT_PASSWORD"' < /some/path/on/your/host/all-databases.sql
```
## Dockerfile - add test db script
```bash
FROM mysql:latest

COPY test_db /usr/app
COPY load-employees.sh /usr/app

```

### load-employees.sh
```bash
cd /usr/app
mysql -uroot -p"$MYSQL_ROOT_PASSWORD" < employees.sql
```

## docker exec
```bash
docker exec d8a sh -c '/usr/app/load-employees.sh'
```
