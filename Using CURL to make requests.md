## GET requests
``` shell
curl http://example.com/abc
```

## Specifying a Request's HTTP method
By default, `curl` makes `GET` requests, but you can use the `-X` option (short for `--request`) followed by the HTTP verb (eg. `PUT`, `POST`, `DELETE`, etc.) of your choice to make other types of requests.

Delete request example:
``` shell
curl -X DELETE http://sample-api.com/sample-resource/id
```

## Adding data to the Request
To send data in the body of a request made with `curl`, you can use the `-d` option (short for `--data`) followed by the data you wish to send.

``` shell
curl -X PUT -d "username=Lily" http://sample-api.com/users/1
```

Additional key-value pairs can be added with the ampersand `&` symbol:

``` shell
curl -X PUT -d "username=Lily&height=180" http://sample-api.com/users/1
```

**NOTE:** that if you include the `-d` option and do not specify an HTTP verb, `curl` will default to sending a `POST` request.

## Setting the Request’s Content Type
By default, `curl` sends `POST/PUT` requests with the content-type `application/x-www-form-urlencoded`. If you are using `curl` to make a request to an API that expects to receive data in JSON format, you must set the request’s content-type to `application/json` by adding a request header.

Use the `-H` (short for `--header`) option, followed by the header you wish to add.

``` shell
curl -d "{ \"username\": \"Lily\" }" -H "Content-Type: application/json" http://sample-api.com/users
```

## Parsing Server Responses
When you make a request with `curl`, `curl` will default to only outputting the response body to the command shell.

Adding the `-i` option (short for `--include`) to your `curl` commands will cause `curl` to print the response header to the command shell in addition to the response body.

Example:
``` shell
$ curl -i https://api.coinbase.com/v2/prices/BTC-USD/buy  
  
HTTP/2 200  
date: ...  
content-type: ...  
...
```

