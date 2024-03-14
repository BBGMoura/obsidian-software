## Hibernate Object States
**Transient**
A **new** instance of a persistence class which is not associated with a session has no representation in the database. This value is considered **transient** by Hibernate.

``` java
Person person = new Person();
person.seyName("Foobar");
```

**Persistent**
A **persistent** instance has a representation in the database, an identifier value and is associated with a Session. You can make a transient state persistent by allocating it with a session:

``` java
Long id = (Long) session.save(person);
```

If we close the Hibernate Session, the persistent instance will become a detached instance. _Note_: it can be modified and reattached to a new Session later.

![[hibernate object states.png]]
