HTTP stands for Hypertext Transfer Protocol. It is used to structure request and responses over the internet. 

The transfer of resources happens using TCP (Transmission Control Protocol). TCP manages channels between your browser and the server. HTTP is the command language that the devices on both sides of the connection must follow to communicate.

## HTTP Methods
- GET - provides read-only access to a resource
- PUT - used to update ab existing resource or create a new one
- DELETE - removes a resource
- POST - creates a new resource
- PATCH - used for partial update
- OPTIONS - used to get the supported operations on a resource

## HTTP Request
Has 5 major parts:
- Verb - HTTP method
- URI - Uniform Resource Identifier to identify resource on server
- HTTP Version 
- Request Header
- Request Body - resource representation

URI examples:
`<protocol>://<service-name>/<ResourceType>/<ResourceID>`

example : POST /api/tutorials

## HTTP Status
HTTP status code are standard codes and referred to predefine status of task done at server. 

- 200 - Ok success
- 201 - created (used for post and put), return new resource using location header
- 204 - no content (when a delete is carried)
- 304 - not modified, used to reduce network bandwidth usage in case of conditional GET
- 400 - bad request, invalid input
- 401 - forbideen, no access to method used
- 404 - not found