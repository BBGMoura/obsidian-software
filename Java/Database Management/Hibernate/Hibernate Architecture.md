
Hibernate has layered architecture which helps the user to operate without knowing the underlying APIs. It uses the database and configuration data to provide persistence services to the application.

Hibernate is an Object Relational Mapping tool. ORM maps object fields to columns in the database of the entity.

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
