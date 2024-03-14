An entity is a java object which is mapped to a database record (or row) .

Entity classes include the Id, unlike DTO classes.

``` Java
package com.mycompany.propertymanagement.entity;  
  
import jakarta.persistence.*;  
import lombok.Getter;  
import lombok.NoArgsConstructor;  
import lombok.Setter;  
  
@Entity  
@Table(name="PROPERTY_TABLE")  
@Getter  
@Setter  
@NoArgsConstructor  
public class PropertyEntity {  
    @Id  
    @GeneratedValue(strategy= GenerationType.AUTO)  
    private Long id;  
    private String title;  
    private String description;  
    private String ownerName;  
    private String ownerEmail;  
    private Double price;  
    private String address;  
}
```