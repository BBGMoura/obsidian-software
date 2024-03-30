In the application.properties file, we can define values for different spring profiles.

For example, in our application-dev.properties profile, we can define a database url value:

``` properties
spring.datasource.url = jdbc:h2:file:~/h2/pmsdb
```

For this value to be injected, we must use the following annotation:
``` java
@Value("${spring.datasource.url}")
private String databaseUrl;
```

This makes it possible to have different values for different spring profiles.

You can use : for a default value:
``` java
@Value("${spring.datasource.url:}")
```