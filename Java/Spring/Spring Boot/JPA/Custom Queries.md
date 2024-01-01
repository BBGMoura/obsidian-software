Custom filter queries can be added to extend the CRUD repository. All that is required is to add a properly formatted method name to the interface.

For example:
``` java
package com.codecademy.people.repositories;  
  
import java.util.List;  
  
import org.springframework.data.repository.CrudRepository;  
  
import com.codecademy.people.entities.Person;  
  
public interface PersonRepository extends CrudRepository<Person, Integer> {  
  // this declaration is all we need!  
  List<Person> findByEyeColor(String eyeColor);  
}
```

Spring Data JPA will automatically generate the "implementation" of the method when the application is compiled. 

To call this in the controller, we use the method:
``` java
@GetMapping("/people/search")  
public List<Person> searchPeople(  
  @RequestParam(name = "eyeColor", required = false) String eyeColor  
) {  
  if (eyeColor != null) {  
    return this.personRepository.findByEyeColor(eyeColor)  
  } else {  
    return new ArrayList<>();  
  }  
}
```

**@RequestParam(name = "eyeColor", required = false)**
This is the common convention in REST APIs when passing parameters used for searching or filtering.

The request would look like:
``` bash
curl localhost:4001/people/search?eyeColor=brown
```