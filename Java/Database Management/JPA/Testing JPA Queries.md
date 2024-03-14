The **[@DataJpaTest](https://mkyong.com/spring-boot/testing-spring-data-jpa-with-datajpatest/)** annotation can be used to write integration tests between the code and databases. 

It does the following:
- It scans the **@Entity** classes and Spring Data JPA repositories.
- Sets the `spring.jpa.show-sql` property to true and enables the SQL queries logging.
- By default, JPA test data is transactional. It rolls back at the end of each test. No clean up required.
- Replace the application data source, run and configure the embedded database on classpath. This uses a H2 database.

## @DataJpaTest
Below shows a setup for a test of a `BookRepository`.

``` java
@DataJpaTest public class BookRepositoryTest {

// Alternative for EntityManager 
// Optional in this case, we can use bookRepository to do the same stuff 
@Autowired 
private TestEntityManager testEntityManager;

//this is testing JpaRepo not CrudRepo
@Autowired 
private BookRepository bookRepository;

@Test 
public void testSave() { 
	Book b1 = new Book("Book A", 
						BigDecimal.valueOf(9.99),
						LocalDate.of(2023, 8, 31));
						
	//testEM.persistAndFlush(b1); the same
	bookRepository.save(b1); 
	
	Long savedBookID = b1.getId(); 
	
	// Book book = testEM.find(Book.class, savedBookID);  the same
	Book book = bookRepository.findById(savedBookID).orElseThrow(); 
	
	assertEquals(savedBookID, book.getId()); 
	assertEquals("Book A", book.getTitle()); 
	assertEquals(BigDecimal.valueOf(9.99), book.getPrice()); 
	assertEquals(LocalDate.of(2023, 8, 31), book.getPublishDate()); 
}

@Test 
public void testUpdate() 
{ 
	Book b1 = new Book("Book A", 
						BigDecimal.valueOf(9.99),
						LocalDate.of(2023, 8, 31));
						 
	//testEM.persistAndFlush(b1); 
	bookRepository.save(b1); 
	// update price from 9.99 to 19.99 
	b1.setPrice(BigDecimal.valueOf(19.99)); 
	// update bookRepository.save(b1); 
	List<Book> result = bookRepository.findByTitle("Book A");
	
	assertEquals(1, result.size()); 
	Book book = result.get(0); 
	assertNotNull(book.getId()); assertTrue(book.getId() > 0); 
	assertEquals("Book A", book.getTitle()); 
	assertEquals(BigDecimal.valueOf(19.99), book.getPrice()); 
	assertEquals(LocalDate.of(2023, 8, 31), book.getPublishDate()); 
}

@Test 
public 
void testFindByTitle() { 
	Book b1 = new Book("Book A", 
						BigDecimal.valueOf(9.99), 
						LocalDate.of(2023, 8, 31));
						
	bookRepository.save(b1); 
	
	List<Book> result = bookRepository.findByTitle("Book A");
	
	assertEquals(1, result.size()); 
	Book book = result.get(0); 
	assertNotNull(book.getId()); 
	assertTrue(book.getId() > 0); 
	
	assertEquals("Book A", book.getTitle());
	assertEquals(BigDecimal.valueOf(9.99), book.getPrice());
	assertEquals(LocalDate.of(2023, 8, 31), book.getPublishDate()); 
}

@Test 
public void testFindAll() { 
	Book b1 = new Book("Book A", 
						BigDecimal.valueOf(9.99),
						LocalDate.of(2023, 8, 31)); 
						
	Book b2 = new Book("Book B", 
						BigDecimal.valueOf(19.99),
						LocalDate.of(2023, 7, 31)); 
						
	Book b3 = new Book("Book C", 
						BigDecimal.valueOf(29.99), 
						LocalDate.of(2023, 6, 10)); 
	
	Book b4 = new Book("Book D", 
						BigDecimal.valueOf(39.99),
						LocalDate.of(2023, 5, 5));
						
	bookRepository.saveAll(List.of(b1, b2, b3, b4));
	List<Book> result = bookRepository.findAll(); 
	assertEquals(4, result.size()); 
}

@Test 
public void testFindByPublishedDateAfter() { 
	Book b1 = new Book("Book A", 
						BigDecimal.valueOf(9.99), 
						LocalDate.of(2023, 8, 31));
						
	Book b2 = new Book("Book B", 
						BigDecimal.valueOf(19.99), 
						LocalDate.of(2023, 7, 31)); 
						
	Book b3 = new Book("Book C", 
						BigDecimal.valueOf(29.99), 
						LocalDate.of(2023, 6, 10)); 
						
	Book b4 = new Book("Book D", 
						BigDecimal.valueOf(39.99), 
						LocalDate.of(2023, 5, 5));
						
	bookRepository.saveAll(List.of(b1, b2, b3, b4)); 
	List<Book> result = bookRepository.findByPublishedDateAfter( LocalDate.of(2023, 7, 1)); 
	// b1 and b2 
	assertEquals(2, result.size()); 
} 

@Test 
public void testDeleteById() { 
	Book b1 = new Book("Book A", 
						BigDecimal.valueOf(9.99), 
						LocalDate.of(2023, 8, 31));
						
	bookRepository.save(b1); 
	Long savedBookID = b1.getId(); 
	
	// Book book = bookRepository.findById(savedBookID).orElseThrow(); 
	// Book book = testEM.find(Book.class, savedBookID); 
	
	bookRepository.deleteById(savedBookID); 
	
	Optional<Book> result = bookRepository.findById(savedBookID); 
	assertTrue(result.isEmpty());
}
```


Another example:
``` java
@Test 
public void whenFindByName_thenReturnEmployee() { 
	// given 
	Employee alex = new Employee("alex");
	entityManager.persist(alex); 
	entityManager.flush(); 
	// when 
	Employee found = employeeRepository.findByName(alex.getName()); 
	// then 
	assertThat(found.getName()) .isEqualTo(alex.getName()); 
}
```

### SQL Query Logging Settings
By default, SQL query logging is enabled. Therefore, the queries will be logged onto the terminal.

We can set the `spring.jpa.show-sql` property to false to turn off this logging.

``` java
@DataJpaTest(showSql = false) 
public class BookRepositoryTest { //...}
```

### Transactional and Roll Back Settings
By default, the test data is transactional and roll back at the end of every test. 

We can add an **@Transactional** annotation to change this:
``` java
@DataJpaTest 
@Transactional(propagation = Propagation.NOT_SUPPORTED) public class BookRepositoryTest { //... }
```

We can also use the **@Rollback** annotation to prevent the roll back of data.
``` java
// We can do his at a class level
DataJpaTest
@Rollback(false)
public class ProductRepositoryTests {

//or at a method level
 @Test
 @Rollback(false)
 public void testSaveNewProduct() {

```
### @AutoConfigureTestDatabase
By default, the **@DataJpaTest** uses **@AutoConfigureTestDatabase** to replace the data source, run and configure an embedded database on the classpath. 

This feature can be turned off by adding an attribute to the annotation:

``` java
// We dont want the H2 in-memory database
// We will provide a custom `test container` as DataSource

@DataJpaTest 
@AutoConfigureTestDatabase(replace = AutoConfigureTestDatabase.Replace.NONE) 
public class BookRepositoryTest { //... }
```

This is helpful when using [test containers](https://mkyong.com/spring-boot/spring-boot-spring-data-jpa-postgresql/#testing-rest-services-rest-assured-and-testcontainers). 

Example:
``` java
@DataJpaTest 
@AutoConfigureTestDatabase(replace = AutoConfigureTestDatabase.Replace.NONE) 
@Testcontainers 
public class BookRepositoryTest { 
	// static, all tests share this postgres container @Container 
	@ServiceConnection 
	static PostgreSQLContainer<?> postgres = new PostgreSQLContainer<>( "postgres:15-alpine" ); 
	//... 
}
```

