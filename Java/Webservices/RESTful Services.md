A webservice is a collection of open protocols and standards used for exchanging data between applications or systems.

REST stands for representation state transfer. REST services want to make best use of HTTP.

REST  request and response are in a format which is defined by HTTP - Hyper Text Transfer Protocol. 

HTTP makes different requests such as POST, GET, PUT, DELETE, PATCH. They have status codes such as 1xx, 2xx, 3xx, 4xx, 5xx.

## Resource
Is anything you want to expose to the outside world from your application - they represent a specific item of data.  

Resources are addressable by URIs uniform resource identifier.
HTTP methods are used to perform operations on resources.

REST uses several representations to represent a resource. Such as text, JSON, XML.

Webservices based of REST Architecture are known as restful webservices. These web services use HTTP methods to implement the concept of REST architecture. A RESTful webservice usually defines a URI (Uniform Resource Identifier) a service, provides resource representation such as JSON and a set of HTTP methods.

REST webservices use HTTP protocol for data communication.

A RESTful webservice should not keep client state on server. It is called stateless. One request will not know about the other. It is responsibility of the client to pass context using a session identifier.

## Resource Definition
Swagger