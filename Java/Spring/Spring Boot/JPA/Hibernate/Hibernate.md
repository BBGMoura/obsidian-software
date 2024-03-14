JPA is just a specification. It has only given how to implement things and not actually implemented it. In other words, it is interfaces. Hibernate is the actual implementation framework.

Hibernate has layered architecture which helps the user to operate without knowing the underlying APIs. It uses the database and configuration data to provide persistence services to the application.

Hibernate is an Object Relational Mapping tool.

![[hibernate.png]]

### Configuration Object
Configuration object is the first Hibernate object you can create in any Hibernate application. It is usually created once during application initialisation.

It provides 2 key  components:
- Database Connection configuration
- Class Mapping Setup
### SessionFactory Object
Configuration object is then used to create a SessionFactory object. It helps us create one connection to the database.

It is a thread safe object and used by all the thread of an application. 

We would need one SessionFactory object per database using a separate configuration. So it makes one connection per database.

### Session Object
A Session is used to get a physical connection with a database. The SessionFactory is used to create a Session object. There can be multiple sessions for each databases. This is to have many queries running at the same time.

Therefore, the session object is lightweight and designed to be instantiated each time an interaction is needed with the database.

### Transaction Object
A transaction represents a unit of work with the database. A transaction should be complete, and if not complete, the database will roll back to the original state.

### Query Object
Query objects use SQL or Hibernate Query Language string to retrieve data from the database.

### Criteria Object 
Criteria objects are used to create and execute object oriented criteria to retrieve objects.

This is where there is many WHERE parts to the query.

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

## Hibernate Caching
- Caching is a mechanism to enhance the performance of a system. 
- It is a buffer memory that lies between the application and the database.
- Instead of making the query to the database consistently, we ask hibernate to cache it.
- Cache memory stores recently used data items in order to reduce the number of database hits.

Hibernate utilises multilevel caching:
### Levels of Caching
**First-Level Caching**
The first-level cache is the Session cache and is mandatory cache though which all requests must pass. The Session object keeps an object under its own power before committing it to the database.

**Second-Level Caching**
Second-level cache is an optional cache. It is on the factory level. This cache can be configured on a per-class and per-collection basis and mainly responsible for caching objects across sections.

**Query-level Cache**
Hibernate also implements a cache for query result-sets that integrates closely with he second level cache.

This is an optional feature which requires two additional physical cache regions that hold the cached query results and timestamp of when a able was last updated. This is useful for queries which are ran frequently with the same parameters.

![[hibernate cache.png]]

## JPA or Hibernate Properties
