Entities in JPA are POJOs (plain old java object) representing data that can be persisted in the database.

We define an entity with the use of the **@Entity** notation.  The name defaults to the name of the class, however we can change the name using **@Entity(name="name")** .

**We must make sure the entity has a no-arg constructor and a primary key.**

__The entity classes must not be declared as final.__

You can find annotations in the javax.persistence.
## Different annotations:
**@Id**
Each JPA entity must have a primary key that uniquely identifies it. We can generate identifiers in different ways , which are specified by the **@GeneratedValue** annotation.

There are four generation strategies: 
- AUTO
- TABLE
- SEQUENCE
- IDENTITY

``` java
@Id 
@GeneratedValue(strategy=GenerationType.AUTO) 
private Long id;
```

If we specify `GenerationType.AUTO`, the JPA provider will use any strategy it wants to generate the identifiers.

**@Table**
In most cases, the name of the table in the database and then name of the entity wont be the same.

In these cases, we specify the table name using the **@Table** annotation:
``` java
@Entity 
@Table(name="STUDENT", schema="SCHOOL") 
public class Student { 
// fields, getters and setters 
}
```

We can mention the name of the table and the name of the schema.

NOTE: If we don't use the table annotation, the name of the table will be the name of the entity.

**@Column**
This annotation defines the details of the column in the table. It has elements such as name, length, nullable, and unique.

``` java
@Column(name="STUDENT_NAME", length=50, nullable=false, unique=false) 
private String name;
```

name -> specifies the name of the column in the table
length -> specifies max length
nullable -> specifies if the field has to be unique

If we don’t specify this annotation, the name of the column in the table will be the name of the field.

**@Transient**
This annotation makes the field non-persistent. The field will not be recorded in the database.

``` Java
@Transient private Integer age;
```

**@Temporal**
This is used for temporal values in our database:
``` java
@Temporal(TemporalType.DATE) 
private Date birthDate;
```

NOTE: however, with JPA 3.1, we also have support for _java.time.LocalDate, java.time.LocalTime, java.time.LocalDateTime, java.time.OffsetTime_ and _java.time.OffsetDateTime._

**@Enumerated**
This allows the persistence of an enum. The annotation can specify whether the enum should be persisted by name or ordinal (default).

```java
public enum Gender { 
	MALE, 
	FEMALE 
}
```

``` java
@Enumerated(EnumType.STRING) 
private Gender gender;
```

We **don’t have to specify the _@Enumerated_ annotation at all if we’re going to persist the _Gender_ by the _enum_‘s ordinal.**

However, to persist the Gender by enum name (MALE, or FEMALE), we’ve configured the annotation with _EnumType.STRING._

**@

