A Spring Bean is an object managed by the Inversion of Control (IoC) container. The Spring IoC container's management of beans includes several responsibilities.  The most significant includes bean instantiation/assembly and management of dependency injection.

Bean is just a Java class whose object creation and destruction is managed by Spring framework.

## @Bean
If we create a method which creates a new object. This will return a singleton bean.

``` java
@Bean
public BeanDemo beanDemo(){
	return new BeanDemo();
}
```
## Bean Instantiation
``` java
@Component  
public class RaceTrack {  
  private String location;  
  private int miles;  
  private String trackType;  
}  
  
@Component  
public class Driver {  
  private String name;  
  private String team;  
  private int yearsExperience;  
}

public class RaceRound {  
  private String startTime;  
  @Autowired  
  private RaceTrack currentRaceTrack;  
  @Autowired  
  private Driver currentDriver;  
}

```

We must annotate the involved classes with **@Component**. In addition, we use the **@Autowire** instead of instantiating `RaceTrack` and `Driver`. 

The **@Autowired** annotation is a way to pass one instance of one object to another class instance. This functionality is also known as object autowiring.

We marked the classes `RaceTrack` and `Driver` as Spring beans. This allows the IoC to manage them.

Alternatively, if we inject dependency via a constructor, we do not need to annotate them with **@Autowire**. This method does not need any annotations.

``` java
public class CoffeeController {  
  
  private final CoffeeRepository coffeeRepository;  
  
  public CoffeeController(CoffeeRepository coffeeRepo) {  
    this.coffeeRepository = coffeeRepo;  
  }  
}
```


## Spring Io
For spring to take control of the dependency injection of different classes, the following annotations must be used:
- **@RestControlller**
- **@Controller**
- **@Service**
- **@Component**

