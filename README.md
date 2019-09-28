# Postgres Docker Camunda
Executar o docker
```
$ docker run -d -p 5432:5432 --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword postgres

```
Editar o volume
```
docker exec -it my-postgres bash
```
Acessar o banco via psql
```
psql -h localhost -p 5432 -U postgres -W
```
Para criar um usuário no Postgres
```
su - postgres
```
```
$ createuser testuser
$ createdb testdb
$ psql ( enter the password for postgressql)
$ alter user testuser with encrypted password 'qwerty';
$ grant all privileges on database testdb to testuser;
```
Application.yaml
```
spring:
  datasource:
    driver-class-name: org.postgresql.Driver
    url: jdbc:postgresql://localhost:5432/camunda
    username: postgres
    password: mysecretpassword
```
Oracle
```
spring:
  datasource:
     driver-class-name: oracle.jdbc.driver.OracleDriver
     url: jdbc:oracle:XXX:@XXX:XXX/XXX
     username: XXX
     password: XXX
```
pom.xml
```
    <dependency>
      <groupId>org.postgresql</groupId>
      <artifactId>postgresql</artifactId>
      <version>42.2.5</version>
    </dependency>
```
