**Web Service - a Software system designed to support interoperable machine-to-machine interaction over a network.**

3 Keys
- designed for application to application interaction 
- interoperable - not platform dependent
- should allow communication over a network

## How does data exchange between two applications take place?
Communicates using HTTP Protocol.

Application sends webservice and request.
Webservice then returns with a response

The request and response should be in formats that all applications should understand as webservices should be platform independent.

Examples of popular formats:
- XML (Extensible Markup Language)
- JSON (javascript object notation)
\
## How do applications know the format of the data?
- Service Provider - Server : The application which is providing the service
- Service Consumer - Client: The application which is using the service
- Service Definition : contract between the server and the client 

Service definition -> specifies the following things:
- request/response format
- request structure
- response structure
- endpoint

## Transport
Transport defines how the service is called.
Two popular types are HTTP and MQ.

HTTP is over over the internet. Using URL to contact endpoints.

MQ is communication over a queue. The service requester will put a request in the queue. The service provider would be listening on the queue. It will take the request, process and return the response to the queue, where the service consumer can access it.


## Types
There are two different types of webservices:
- [[RESTful Services]]
- [[SOAP]]

Note: SOAP and REST are not directly comparable. REST defines an architectural approach. SOAP poses restrictions on the XML which is exchanged between your service provider and service consumer.
