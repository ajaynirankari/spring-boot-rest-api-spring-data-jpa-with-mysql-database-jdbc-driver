# spring-boot-rest-api-spring-data-jpa-with-mysql-database-jdbc-driver

Reference source: https://spring.io/guides/gs/accessing-data-mysql/


MySQL Database setup
1. Install MySQL
2. Login MySQL
3. Create the Database from below commands
   ```
   create database user_db;
   create user 'testUser'@'%' identified by 'testUser';
   grant all on user_db.* to 'testUser'@'%';
   ```

Spring MySQL configuration from file - src/main/resources/application.properties

```
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://localhost:3306/user_db
spring.datasource.username=testUser
spring.datasource.password=testUser
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.show-sql=true

```

Steps to Run Application
1. Open Git Bash
2. git clone https://github.com/ajaynirankari/spring-boot-rest-api-spring-data-jpa-with-mysql-database-jdbc-driver.git
3. cd spring-boot-rest-api-spring-data-jpa-with-mysql-database-jdbc-driver/
4. ./mvnw clean spring-boot:run

Steps to Test Application
1. Open Git Bash
2. curl -v http://localhost:8080/users | jq
```
$ curl -v http://localhost:8080/users | jq
*   Trying 127.0.0.1:8080...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0* Connected to localhost (127.0.0.1) port 8080 (#0)
> GET /users HTTP/1.1
> Host: localhost:8080
> User-Agent: curl/7.78.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200
< Content-Type: application/json
< Transfer-Encoding: chunked
< Date: Thu, 09 Nov 2023 06:29:34 GMT
<
{ [160 bytes data]
100   154    0   154    0     0  23273      0 --:--:-- --:--:-- --:--:-- 30800
* Connection #0 to host localhost left intact
[
  {
    "id": 52,
    "name": "Ranjan",
    "email": "ranjan@gmail.com"
  },
  {
    "id": 53,
    "name": "Smith",
    "email": "Smith@gmail.com"
  },
  {
    "id": 54,
    "name": "John",
    "email": "John@gmail.com"
  }
]

```
   
