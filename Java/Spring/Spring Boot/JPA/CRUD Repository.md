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