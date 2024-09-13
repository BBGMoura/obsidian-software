Simple Object Access Protocol (SOAP)  defines a specific way of building a webservice. t defines a specific format for your request and your response. It does not add restrictions to your transport.

XML is used for the format fore Requests and Responses.

SOAP defines a specific XML Request and Response format.

You have to create an Envelope.
This will include a Header and a Body.

![[SOAP.png]]

**Example Response**

``` XML
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/">
	<SOP-ENV:Header/>
	<SOAP-ENV:Body>
		...
	</SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## Transport
There no restrictions on transport. We can use both HTTP or MQ.

## Service Definition
Service definition is typically done using a Web Service Definition Language (WSDL).

It defines:
- endpoint
- all operations
- request structure
- response structure