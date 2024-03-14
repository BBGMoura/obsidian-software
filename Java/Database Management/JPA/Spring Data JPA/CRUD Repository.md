Spring Boot's CRUD repository is a part of the Spring Data JPA framework, which provides convenient methods for performing CRUD operations on entities in a relational database.

CrudRepository is an interface that extends the basic Repository interface and adds generic CRUD methods to it.

To use the CrudRepository, an interface which extends the CrudRepository interface has to be created.

``` java
public interface CrudRepository<T, ID> extends Repository<T, ID>

//Example
@Repository
public interface DepartmentRepository extends CrudRepository<Department, Long> {}
```

where:
- T = domain type that repository changes (Entity/Model class name)
- ID = type of id which the repository manages

## Most Important Methods
1. save()
Saves an entity. Use the returned instance for further operation as the entity might have changed completely.

2. findById()
Retrieves entity by Id. It will return the entity or an Optional#empty() if none is found.

3. findAll()
Returns all entities of the type. 

4. count()
Returns the number of entities available in type `long`.

5. deleteById()
Deletes the entity with the given id.

## DTO
model and DTOs are interchangeable names. QAs they are both data transfer objects. Only the Entity talks to the database.

DTO is used to hold data in the controller and service layer.

A DTO class example using lombok annotation:

``` java
@Getter  
@Setter  
public class PropertyDTO {  
    private String title;  
    private String description;  
    private String ownerName;  
    private String ownerEmail;  
    private Double price;  
    private String address;  
}
```

You can use **@JsonProperty** to map the name of the fields of an object to a diff name for example:

``` java
public class CalculatorDTO {
	@JsonProperty("num")
	private Double num1;
}
```

This makes it so when a http request is sent with a JSON body, if it contains "num", this will be mapped to num1 field in the CalculatorDTO object.

