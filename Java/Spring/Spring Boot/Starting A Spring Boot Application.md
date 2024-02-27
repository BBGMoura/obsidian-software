
The **@SpringBootApplication** annotation is a compilation of different annotations which automatically instantiates beans from the found components.

``` java
@SpringBootApplication  
public class RecipeApplication {  
  
  public static void main(String[] args) {  
    SpringApplication.run(RecipeApplication.class, args);  
  }  
}
```


The `@SpringBootApplication` annotation is a compilation of `@Configuration`, `@ComponentScan`, and `@EnableAutoConfiguration`. When we apply the `@SpringBootApplication` annotation to the class containing our main method, our application runs with all of this built-in functionality.

- `@Configuration`, which notifies the framework that beans may be created via the annotated class.
- `@ComponentScan`, which tells the framework to scan our code for components such as classes, controllers, services, etc.
- `@EnableAutoConfiguration`, which tells the container to auto-create beans from the found components.

This also automatically runs a Tomcat server for us. We can see in the terminal when we run the application:

``` shell
2024-02-27T15:12:59.614Z  INFO 21364 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port 8080 (http)

```

We can change where the port is ran by adding the following to the application.properties file:

``` properties
server.port = 8089
```

