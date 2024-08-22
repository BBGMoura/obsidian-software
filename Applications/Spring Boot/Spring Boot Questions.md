1. What is REST
Representational State Transfer. Uses HTTP Protocol to send data.

2. What is a resource?
A resource is how data is represented in REST architecture. Clients can read, write, modify and create resources using HTTP methods

3. Safe REST operations?
Safe -> do not modify data. So GET and HEAD

4. Idempotent operations? Why is idempotency important?
Idempotent operations return same response no matter how many times you call it. Like GET.

POST is not idempotent as it will result in multiple resource creations.

PUT is idempotent if you are using it to update the resource.

5. Is rest scalable and/or interoperable?
Yes they are scalable and interoperable. You can create a rest application with all languages, and any technology can consumer on client or server end. 

6. What are IOC?
- bean factory
- applicationcontext