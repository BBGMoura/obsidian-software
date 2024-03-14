model and DTOs are interchangeable names. QAs they are both data transfer objects. Only the Entity talks to the database.

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

The DTO does not need the object's ID.

## Adaptor Design Pattern
DTO is used to hold data in the controller and service layer. The repository layer expects a entity, so we must adapt the DTO in the service layer to an entity to be used in the repository.

Vise versa we must convert a entity to DTO so return to the controller.

_NOTE_
You can use **@JsonProperty** to map the name of the fields of an object to a diff name for example:

``` java
public class CalculatorDTO {
	@JsonProperty("num")
	private Double num1;
}
```

This makes it so when a http request is sent with a JSON body, if it contains "num", this will be mapped to num1 field in the CalculatorDTO object.

