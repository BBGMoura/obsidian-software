Mockito is an open-source testing framework used for unit testing. It is used to mock interfaces so that a dummy functionality can be added to a mock interface that can be used in Unit Testing.

Unit Testing is a type of software testing in which individual software components are tested.

Mockito can be used with other testing frameworks like JUnit and TestNG.
## @Mock
-  Creates a mock.
- Is used to create mocks that are needed to support the testing of the class to be tested.
- Annotated class to be tested dependencies with @Mock annotation.
- We must define the when-thenReturn methods for mock objects and which class methods will be invoked during actual test execution.
## @InjectMocks
- @InjectMocks creates an instance of the class and injects the mocks that are created with the @Mock annotations into this instance.
- @InjectMocks is used to create class instances that need to be tested in the test class.
- @InjectMocks is used when the actual method body needs to be executed for the given class.
- Use @InjectMocks when we need all internal dependencies initialised with mock objects to work the method correctly.

``` Java
@RunWith(MockitoJUnitRunner.class)
class StudentTest {
	@Mock
	Pen pen; 
	
	@InjectMocks
	Student student; 
	
	@Test
	public void writeWithPenTest() throws Exception 
	{ 
		Mockito.when(pen.getRedPen()).thenReturn("Red Pen"); 
		assertEquals("Student Write with: Red Pen", student.write()); 
	} 

}
```

