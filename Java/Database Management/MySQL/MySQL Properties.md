
To connect to a MySQL database, we must import the MySQL connector. We can do this with the following dependency in the pom.xml file:

``` xml
<dependency>  
    <groupId>mysql</groupId>  
    <artifactId>mysql-connector-java</artifactId>  
    <version>8.0.33</version>  
</dependency>
```

## Properties
``` properties
spring.datasource.url=jdbc:mysql://localhost:3306/dbname?useSSL=false&serverTimezone=UTC&useLegacyDatetimeCode=false  
spring.datasource.username=root  
spring.datasource.password=  
spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver  
  
spring.jpa.hibernate.d
dl-auto=update  
spring.jpa.show-sql=true  
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
spring.jackson.serialization.fail-on-empty-beans=false
```

