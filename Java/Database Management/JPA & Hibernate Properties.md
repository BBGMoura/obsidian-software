When the Spring Boot application starts, it will check the properties file, located at **src/main/resources/application.properties**, for configurations. 

``` java
//database
spring.datasource.url=jdbc:h2:file:~/h2/pmsdb
spring.datasource.username=sa //database username
spring.datasource.password= //database password

//jpa
spring.datasource.driverClassName= org.h2.Driver //JDBC for h2 database (thias value will be diff for each database like mySQL) It tells how to conver the query we have written to the DB lanaguage
spring.jpa.hibernate.ddl-auto=update 
//update -> tables will be created only the first time the application starts.
//create -> drops and creates tables on start and stop.
spring.jpa.show-sql=true
//prints sql queries in logs/console
spring.jpa.properties.hibernate.format_sql=true 
//prints sql in formatted way
spring.jpa.database-platform=prg.hibernate.dialectH2Dialect
//this prpertye makes Hibernate generate the appropriate SQL for chosen table
```