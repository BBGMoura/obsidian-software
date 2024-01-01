**Java Persistence API, a specification for the set of interfaces to store, query and update data stored in a database.**

**A data model is a set of objects that are designed to uniquely represent the concepts compromising your problem domain, whose data will want to ultimately store in a database.**

Adding a database is easy to do with the help of a library called Spring Data JPA. Java Persistence API (JPA) is the underlying standard used to translate objects from Java into queries that can be sent directly to the underlying database.

Spring Data JPA "wraps" around an implementation of the JPA to make it seamless process to integrate a database into a Spring Boot Application.

JPA wraps around another standard, JDBC (Java Database Connectivity). This is the layer that sends raw database queries to the underlying database.

JPA is a standard that can be implemented by an ORM (object-relational mapping). The purpose of an ORM is to allow application developers to implement the required interactions with the underlying database without having to actually write database queries.

Instead, developers are able to work with easy-to-understand objects in their code, that the ORM “translates” or maps into queries against the underlying database relations.

For example, instead of defining a database table in SQL…
```
CREATE TABLE plants (  name varchar,  type varchar,);
```
…we can define a plain-old Java class:
```
public class Plant {  private string name;  private string type;}
```

Instead of writing SQL queries…
```
SELECT nameFROM plantsWHERE name='ficus';
```
…we can use Java methods:
```
Plant ficusName = plantRepository.findByName('ficus').name;
```

### Hibernate
The ORM most commonly used with Spring Data JPA is called Hibernate. It comes with the Spring Data dependency `spring-boot-starter-data-jpa`.

## Database Types
Spring Data JPA supports many different kinds of databases right out of the box. This means the code remains the same for each underlying database.

For example, we may start with a database like MySQL, but eventually change it to PostgreSQL. We won't have to change anything about the application logic. You would simply have to changes the configurations to point to the new database.

As long as an appropriate JDBC driver exists for a given database, implementations of the JPA will be able to translate Java objects to the right SQL queries, which might be different between databases.

 A database will run separately from an application, in a different physical location than where the application runs. This is because databases have different requirements than applications in terms of what it takes to keep them running and resilient. _Infrastructure_ is the generic term for the machines that applications and databases run on.

## H2
H2 is a database type. It is a relational database written entirely in Java. It can run on the same kind of infrastructure as your application and can run entirely "in-memory". This makes it easy to use to test your Spring Boot application on your machine, without having to obtain a database server from elsewhere.

To connect yo an embedded H2 database using Spring Data JPA, application properties need to be updated.  The type of information stored inside property files include:
- database URL
- number of logs the application should produce
- the port the application runs on 

When the Spring Boot application starts, it will check the properties file, located at **src/main/resources/application.properties**, for configurations. 

Example (plants.db is the database) :
``` properties
spring.datasource.url=jdbc:h2:~/plants.db  
spring.datasource.driverClassName=org.h2.Driver
```

# Summary
- Spring Data JPA Is available in the `spring-boot-starter-data-jpa` dependency
- Spring Data JPA is an implementation of the Java Persistence API (JPA).
- The object-relational mapping tool, or ORM, provided by Spring Data JPA is called Hibernate. It provides Java methods that can be translated into SQL queries.
- The standard that defines the relationship between Java code and SQL queries is called Java Database Connectivity (JDBC).
- Spring Data JPA  can work with various databases.
- H2 is a database type that can run in memory so developer do not have to set up and connect to a different database.
- The database type is specified in **application.properties**.