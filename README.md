Docker + Alpine-Latest + Mysql/MariaDB-10.1.18

#### parameter

* `MYSQL_ROOT_PWD` : root Password   default "mysql"
* `MYSQL_USER`     : new User
* `MYSQL_USER_PWD` : new User Password
* `MYSQL_USER_DB`  : new Database for new User

#### build image

```
$ docker build -t="davidota/docker-alpine-mysql" .
```

#### run a default contaier

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 davidota/docker-alpine-mysql
```

#### run a container with new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=password -e MYSQL_USER=user1 -e MYSQL_USER_PWD=password1 davidota/docker-alpine-mysql
```

#### run a container with new Database for new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=password -e MYSQL_USER=user1 -e MYSQL_USER_PWD=password1 -e MYSQL_USER_DB=userdb davidota/docker-alpine-mysql
```
