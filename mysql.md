# Mysql Docker run with cases insensitive option
```bash
docker pull mysql
docker run -d --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -e TZ=Asia/Seoul mysql --character-set-server=utf8 --collation-server=utf8_general_ci --lower_case_table_names=1
```

# Mysql Errors
## Public Key retrieval is not allowed( since 8.0)
Add these options to the connection string
* useSSL=false&allowPublicKeyRetrieval=true
