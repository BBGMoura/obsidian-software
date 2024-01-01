When we are building APIs, we want our models to provide four basic types of functionality. The model must be able to Create, Read, Update, and Delete resources. If an action cannot be described by one of these four operations, then it should potentially be a model of its own.

In a REST environment, CRUD often corresponds to the HTTP methods POST, GET, PUT, and DELETE, respectively.

## Create
- uses HTTP POST method.
- creates a new resource of the specified resource type.

Request:
``` shell
POST http://www.myrestaurant.com/dishes/
```
Body:
``` json
{  
  "dish": {  
    "name": “Avocado Toast”,  
    "price": 8  
  }  
}
```
Response:
Status code - 201 (CREATED)
## Read
- uses HTTP GET method

Request:
```
GET http://www.myrestaurant.com/dishes/
```
Response:
Status Code - 200 (OK)

## Update
- uses HTTP PUT method.

Request:
```
PUT http://www.myrestaurant.com/dishes/1223
```
Body:
``` json
{  
	"dish": {    
		"name": “Avocado Toast”,
		"price": 10  
	}
}
```
Response: 
Status Code - 200 (OK)

## Delete
- uses HTTP DELETE method.

Request:
```
DELETE http://www.myrestaurant.com/dishes/1223
```
Response: 
Status Code - 204 (NO CONTENT)