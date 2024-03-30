There are three different types of repositories in Spring Data JPA:
- **CrudRepository** : provides CRUD functions.
- **PagingAndSortingRepository** : provides methods to do pagination and sort records
- **JpaRepository** : provides JPA re
- lated methods such as flushing the persistence context and delete records in a batch

The diagram below shows what methods are available and what each repository extends:

![[Spring Data Repositories.png]]