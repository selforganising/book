#REST
###Representational State Transfer

REST is basically a list of design rules that makes sure that an API is predictable and easy to understand and use.

###Technically ReSTful
* Uniform interface
* Stateless
* Cachable (GETs)
* Client-server
* Layered-system
* Code on demand (optional)

![REST image](http://thefloppydisk.files.wordpress.com/2013/05/web20.png)

**Stateless design**: Data will never be stored in a session (each request includes all information needed by the server and client).
**Self-descriptive messages**: Ideally you should be able to understand requests and responses after spending minimal time reading the documentation.

**Identification of rources** Work with resources not methods. `?area=post` is a BIG clue that the API is *not* ReSTful. 


**Semantics**
The API should use existing features of the HTTP protocol to improve the semanticness of input and output:

HTTP Verbs
```
PUT, POST, GET, DELETE
```

HTTP Status Codes
```
200 OK
201 CREATED
204 NO CONTENT
400 BAD REQUEST
401 UNAUTHORISED
403 FORBIDDEN	 e.g. when been inactive for too long and logged out online banking
404 NOT FOUND
405 METHOD NOT ALLOWED
409 CONFLICT
```


The end points should be human readable: should be obvious what data will be received based on the name. 


```
GOOD: /services/{general-service}

BAD: /nearest/nearestrest.aspx?find=service%20name
```

The end points should be composed of nouns and they should ALWAYS be plural, and words should be separated with hypens. 

```
GOOD: /services/{general-service}/locations/{postcode}

BAD: /nearest/nearestrest.aspx?area=post%20code&find=service%20name
```






##Downsides
Figuring out PUT vs POST (for both client and server developers)





##Things to be aware of…##
* Debate as to when it is OK to call something ReSTful. 
* Originator of the term does not agree with the way his ideas are being implemented. 
* HATEOAS now refers to the purist ReSTful concept.
* APIs can be non-ReSTful e.g. SOAP, XML-RPC
* ReSTful is a new concept


