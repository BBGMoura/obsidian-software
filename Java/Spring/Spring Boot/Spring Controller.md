Spring is a web framework that uses HTTP to build RESTful web services. It enables the application to respond to GET, POST, PUT and DELETE requests.

This example involves a restaurant application. The class is named `RestaurantController`. HTTP  requests are handled by a controller.

``` Java
@CrossOrigin(origins="http://localhost:4200)
@RequestMapping("/restaurants")
@RestController
public class RestaurantController {
}
```

**@RestController**
This annotation tells Spring that this class is a rest controller component.

**@RequestMapping("/restaurants")**
This annotation maps the controller so the requests to `/restaurants` is mapped to this controller.

**@CrossOrigin**
Allows access from any IP address?
## GET
When typing an URL in a browser, this is typically a GET request. The browser displays he response on the browser page. Alternately,  you can use a CURL (client for URLs which is a command line tool).

In order for your application to respond to a GET request, an internal GET method needs to be added in the Spring code. `curl https://webdomain.com/` -> this is a GET request.+

This example method returns a list of restaurants based on their food allergies.

``` Java
@GetMapping  
public Iterable<Restaurant> getAllRestaurants() {  
  return restaurantRepository.findAll();  
}
```

**@GetMapping**
Ensures that GET requests to `/restaurants` are mapped to this `getAllRestaurants()` method.

Alternatively, you can use the annotation:
``` java
@GetMapping("/{id}")
public Restaurant getRestaurant(@PathVariable Long id) {
Optional<Restaurant> restaurant = restaurantRepository.findById(id);
if (restaurant.isPresent()) {
	return restaurant.get();

}
```

**@GetMapping("{id}")**
This ensures that GET requests to `/restaurant/{id}` are mapped to the `getRestaurant()` method.

**@PathVariable**
Used to extract data from the URL path. Defines placeholders in request mapping URL and binds placeholders to method parameters. 

Another annotation is :
``` java
@GetMapping("/get")
public Restaurant getRestaurant(@RequestParam(required = true) Long id) {
Optional<Restaurant> restaurant = restaurantRepository.findById(id);
if (restaurant.isPresent()) {
	return restaurant.get();

}
```

**@RequestParam**
Define the data in the URI in the format: `/restaurants/get?id=[id]`. You can define if is required or not.

You can use **@JsonProperty** to map the name of the fields of an object to a diff name for example:

``` java
public class CalculatorDTO {
	@JsonProperty("num")
	private Double num1;
}
```

This makes it so when a http request is sent with a JSON body, if it contains "num", this will be mapped to num1 field in the CalculatorDTO object.
## POST
POST requests adds new data to a receiving web application. 

We can make POST requests using a curl command:
``` bash
curl -X POST -d "{\"name\":\"Charlie\", \"breed\":\"German Shepherd\"}" -H "Content-Type: application/json" http://www.mypetclinic.com/dogs/
```

- `-X POST` -> tells the server the client is making a POST request. -X is the curl parameter specifying the type of request method to use.
- `-d` -> short for `--data`. Indicates to the server that the client is sending new data.
- `{}` -> content inside the braces is the data being sent in the following format:
``` json
{\"key1\":\"value1\", \"key2\":\"value2\"}
```

- ` -H "Content-Type: application/json"` -> specifies that data is being sent in JSON format.
- `http://www.mypetclinic.com/dogs/` -> URL

``` Java
@PostMapping  
@ResponseStatus(HttpStatus.CREATED)  
public Restaurant addRestaurant(@RequestBody Restaurant restaurant) {  
  validateNewRestaurant(restaurant);  
  return restaurantRepository.save(restaurant);  
}
```

**@RequestBody**
maps the HttpRequest body to a transfer or domain object. It automatically serialises the HttpRequest body on to a Java object.

Spring automatically deserializes JSON into a Java type assuming an appropriate type is specified. Example  object : `'{"username": "johnny", "password": "password"}'`

**@ResponseStatus(HttpStatus.CREATED)**
Used to set the status code of an HTTP response. 

When an endpoint returns successfully, Spring provides an HTTP 200 (OK) response.  In this case, it is returning a HTTP status of created. 

You can also add a reason with the following annotation:
``` java
@ResponseStatus(HttpStatus.BAD_REQUEST, reason = "Some parameters are invalid")
```

NOTES:
- Spring only used the response status when the method completes successfully
- When we set reason, spring calls `HttpServletResponse.sendError()` , so it will send an error page to the client -> this is not a good fit for REST endpoints. https://www.baeldung.com/spring-response-status (convert exception to HTTP response status).

Easiest way to convert an exception to a HTTP response status is using @ResponseStatus to the exception class:

``` java
@ResponseStatus(code = HttpStatus.BAD_REQUEST) class CustomException extends RuntimeException {}
```

You can also throw an exception with a HttpStatus:

``` java
try {  
      int id_int = Integer.parseInt(id)  
      return book.findByID(id_int)  
  } catch (NumberFormatException ex) {  
    throw new ResponseStatusException (HttpStatus.BAD_REQUEST);        
  }
```

## Response Entity
We can send a response using a ResponseEntity in a controller method. We can send a data itself and a type of response code:

``` java
ResponseType<[return-type]> responseEntity = new ResponseEntity<[return-type]> (result, HttpStatus.CREATED);

return responseEntity;
```

Where return type is the type of the result you are returning. In addition, there are various HttpStatus types which can be returned.

For no content returns we can use the example below:
``` java
@DeleteMapping("/delete/{propertyId}")  
public ResponseEntity<Void> deleteProperty(@PathVariable Long propertyId){  
    propertyService.deleteProperty(propertyId);  
    return new ResponseEntity<>(HttpStatus.NO_CONTENT);  
}
```