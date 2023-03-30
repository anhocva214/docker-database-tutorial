### Setup container
```
docker run -p 3306:3306 -d --name mysql -v $(pwd)/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 mysql/mysql-server --bind-address=0.0.0.0
```

### Access CMD to container
```
docker exec -it mysql bash
```

### Create a new user and password
```
CREATE USER 'admin'@'%' IDENTIFIED BY '123456';
GRANT ALL PRIVILEGES ON * . * TO 'admin'@'%';
quit
```

### Access to MySQL by username and password from client
```
mysql -h 127.0.0.1 -P 3306 -u admin -p
```