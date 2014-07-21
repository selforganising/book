#Databases

Databases are a big topic, this is a very quick-and-dirty summary.

##Key-value stores

Analogous to a JavaScript *object*. Data is stored in a *key*, which is used to locate a stored *value*. In other contexts, this sort of data structure can be referred to as a *dictionary*, a *map* or an *associative array*.

The advantage of this sort of storage is that it is fast. The main disadvantage is that it is not very flexible. Imagine a key-value store of user keyed on some unique id, say a username. It is easy to to retrieve their details by username, which is fine if, say, you want to authenticate a user accessing your site. They enter their username and password and your application locates their record and checks the password. But if you want to gather user data based on some other criterion, you are going to have to go through every key and inspect the values stored in each one.

[Redis](http://redis.io/) is a widely-used simple key-value store.

##Document databases

Often referred to as *NoSQL* databases. Based on a simple key-value store, generally storing data as JSON or XML, and using some sort of query language to make access relatively easy.

[MongoDB](http://www.mongodb.org/) is the most widely-used document database. It uses BSON, or binary JSON, allowing large binary objects, such as image files, to be stored efficiently, and offers a relatively simple JavaScript-based API.

Document databases were relatively niche until recently. Now they are widespread. The kinds of data we access and the way we interact with them has changed significantly in recent years. Think: password lookups and retrieving web pages.

MongoDB is going to be our database of choice.

##Relational databases

They are still the dominant form of database in many application areas, but they are not going to covered in this course. If you are thinking of building some sort of heirarchical data structure--an invoicing and stock-control system or a bank clearing system, say--or you have complex reporting requirements--then you are probably going to need to learn about them. 




