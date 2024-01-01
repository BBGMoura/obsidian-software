One Java class can inherit members from another Java class by using the `extends` keyword. 

_When a child class extends a parent, all fields, constructors, and methods become part of the child, except for marked private._ 

A child may still access `private` members indirectly through getters, setters, and other methods.

An **is-a** relationship means that Concept B is some version of Concept A. Usually, it's a more refined or detailed version. In an **is-a** relationship, the more specific concept would inherit from the less specific concept.

A **has-a** relationship defines a connection between two concepts where Concept B uses Concept A as an independent extension of itself. Inheritance isn't appropriate in **has-a** relationships.

Only __is-a__ relationships are candidates for inheritance.

## Relationships
When a class inherits from another class, we say that it _extends_ the class. When `ClassB` extends `ClassA`, it inherits all of `ClassA`'s non-private members. This relationship is named in two ways.

`ClassA` is the **superclass** and `ClassB` is the **subclass**.

This is echoed in the Java keyword `super`. A subclass accesses members in a superclass using the `super` keyword.

You can interchangeably call `Class A` as the parent and `Class B` as the child.

Example:
```java
public class Person {
    // fields
    private String firstName;
    private String lastName;

    // getters and setters
	//...
	
    // constructor
    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    // methods
    public String getFullName() {
        return String.format("%s %s", firstName, lastName);
    }

}
```

Class Student extends Person.
```java
// 1. `extends` pulls all non-priv members from Person
// into Student
public class Student extends Person {

    private String studentId;

    public String getStudentId() {
        return studentId;
    }

    public void setStudentId(String studentId) {
        this.studentId = studentId;
    }

    public Student(String firstName, String lastName, String studentId) {
        // 2. call the constructor on the "super" (or parent) class
        super(firstName, lastName);
        this.studentId = studentId;
    }
}
```

All subclasses must execute the `Person` constructor to initialise the class.

If the superclass does not contain a parameterless constructor, the subclass _must_ call a valid `super` constructor as the first statement in its constructor.

Note: 
For your class `B` to successfully extend `A` you either need:
- A no-args explicit constructor declared in `A`
- Or a call to `super(params)` as first line of `B`'s constructor.

## Validation
The `instanceof` operator detects super-classes and subclasses that are part of the current argument's inheritance hierarchy.

```java
public class App {

    public static void main(String[] args) {

        Person p = new Person("Merilee", "Sheldrick");
        Student s = new Student("Bale", "Packmann", "100-A29-WER");
        Instructor i = new Instructor("Letisha", "Pursey", "INS-COMPSCI-123", "Dr.");

        printPerson(p);
        printPerson(s);
        printPerson(i);
    }

    static void printPerson(Person p) {
        if (p instanceof Person) {
            System.out.println("I'm a Person.");
        }
        if (p instanceof Student) {
            System.out.println("I'm a Student.");
        }
        if (p instanceof Instructor) {
            System.out.println("I'm an Instructor.");
        }
        System.out.println("My name is: " + p.getFullName());
    }
}

/** 
* I'm a Person.
* My name is: Merilee Sheldrick
* I'm a Person.
* I'm a Student.
* My name is: Bale Packmann
* I'm a Person.
* I'm an Instructor.
* My name is: Letisha Pursey 
*/
```

`printPerson()` can take in Student as it is an instance of Person.

## Object

In Java, all classes inherit from the [Object](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Object.html) class implicitly. There's no need to add the `extends` keyword. The compiler adds it for us. There's no way to create a class without extending `Object`.

The following emthods are included in Object:

`toString`
Returns a `String` representation of an object. By default, it returns the class name and a hexidecimal representation of the `hashCode`. That's not very useful, so it's common to override this method. `Empty@7637f22`

`hashCode`
Returns an `int` code that's used for storing an object in hashed data structures. `123961122`

`getClass`
Returns the [Class](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Class.html) associated to the object. An instance of a `Class` contains meta-data (names, parameters, annotations) associated to a class.

`equals`
Returns a `boolean` that indicates if this instance is equal to another object. By default, it evaluates to `true` if the objects share the same memory location -- called **reference equality** -- they share the same reference. It's common to override this method to inspect individual values instead of comparing references.