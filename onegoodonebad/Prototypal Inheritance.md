# Prototypal Inheritance


When it comes to inheritance, JavaScript only has one construct: objects. Each object 

has an internal link to another object called its prototype. That prototype object has a prototype 

of its own, and so on until an object is reached with null as its prototype. null, by definition,

has no prototype, and acts as the final link in this prototype chain.


## Inheritance, the __proto__


  ```var animal = { eats: true }
  
  var rabbit = { jumps: true }
  
  rabbit.__proto__ = animal  // inherit
  
  alert(rabbit.eats) // true```
  
  
  
When a rabbit property is accessed, and the interpreter can’t find it in rabbit, it follows 

the __proto__ link and searches in animal.



  ```var animal = { eats: true }

  rabbit = Object.create(animal)

  alert(rabbit.eats) // true```

info was taken from [http://javascript.info/tutorial/inheritance]

