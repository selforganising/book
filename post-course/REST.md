# REST

#### Representational State Transfer

REST is a list of design rules that makes sure that an API is predictable and easy to understand and use.



## Six technically RESTful requirements

* **Uniform interface**
	The uniform interface constraint defines the interface between clients and servers. It simplifies and decouples the architecture, which enables each part to evolve independently. The four guiding principles of the uniform interface are: 
	* *Identification of resources:*
		Individual resources are identified in requests using URIs as resource identifiers. 
		Work with resources not methods. `?area=post` is a BIG clue that the API is *not* ReSTful. 
	* *Manipulation of Resources Through Representations:*
		When a client holds a representation of a resource, including any metadata attached, it has enough information to modify or delete the resource on the server, provided it has permission to do so.
	* *Self-descriptive messages:*
		Ideally you should be able to understand requests and responses after spending minimal time reading the documentation.
	* *Hypermedia as the Engine of Application State (HATEOAS):*
		Clients deliver state via body contents, query-string parameters, request headers and the requested URI (the resource name).

* **Stateless**
	* Data will never be stored in a session (each request includes all information needed by the server and client).
	* Non-stateless means things have to happen in a certain order and won't work properly if accessed in any other way.

* **Cachable (GETs)**
	* As on the World Wide Web, clients can cache responses.

* **Client-server**
	* The uniform interface separates clients from servers.
	* Servers are not concerned with the user interface or user state, so that servers can be simpler and more scalable.

* **Layered-system**
	* A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way. Intermediary servers may improve system scalability by enabling load-balancing and by providing shared caches. Layers may also enforce security policies.

* **Code on demand (optional)**
	* Servers are able to temporarily extend or customize the functionality of a client by transferring logic to it that it can execute.


![REST image](http://thefloppydisk.files.wordpress.com/2013/05/web20.png)



## Semantics

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
403 FORBIDDEN
404 NOT FOUND
405 METHOD NOT ALLOWED
409 CONFLICT
```

#### Naming Conventions:

* The end points should be human readable: should be obvious what data will be received based on the name. 
* The end points should be composed of nouns and they should be plural.
* Words should be separated with hypens.

BAD:

```
GET /nearest/nearestrest.aspx?area=post%20code&find=service%20name
```

GOOD:
```
GET /services/{general-service}/locations/{postcode}
```



##Things to be aware of…

* Figuring out PUT vs POST (for both client and server developers)
* Debate as to when it is OK to call something ReSTful. However most people think that if you cover all six of the technical requirements that would be enough.
* Originator of the term does not agree with the way his ideas are being implemented. 
* HATEOAS now refers to the purist ReSTful concept.
* APIs can be non-ReSTful e.g. SOAP, XML-RPC
* ReSTful is a new concept



## Resources

* Take a look at the tutorials section: http://www.restapitutorial.com/
* Interesting, however opinionated, history of REST, SOAP, XML and JSON: https://github.com/ServiceStackV3/mythz_blog/blob/master/pages/154.md