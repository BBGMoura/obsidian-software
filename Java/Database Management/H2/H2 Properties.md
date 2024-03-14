These properties go inside resources/application.properties.

``` java
spring.h2.console.enabled=true //allows to see h2 database in browser
spring.h2.console.path=/h2-console //url of h2 database in browser. /h2-consoel is default
spring.datasource.username=sa //database username
spring.datasource.password= //database password

//jpa
spring.datasource.driverClassName= org.h2.Driver //JDBC for h2 database (thias value will be diff for each database like mySQL)
spring.jpa.database-platform=prg.hibernate.dialectH2Dialect
//this prpertye makes Hibernate generate the appropriate SQL for chosen table
```


