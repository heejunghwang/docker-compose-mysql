# Docker Compose MySQL

MySQL is the world's most popular open source database. The default timezone in mysql is UTC time. When you set the timezone in MySQL, you can set the time zone like this.

``` yaml
version: '3.2'

services:
  db:
    image: mysql:5.7
    ports:
      - "3306:3306"
    environment:
      - MYSQL_ROOT_PASSWORD=docker
      - TZ=Asia/Seoul # TimeZone Setting 1
    command: ['mysqld', '--character-set-server=utf8mb4', '--collation-server=utf8mb4_unicode_ci','--default-time-zone=+09:00'] # TimeZone Setting 2

```

## How to run

``` sh
docker-compose up --build
```