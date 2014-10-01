# Methods

There are two main ways objects can be given methods. 

The first is when the object is created:
```
var dog = {	
	bark: function bark() {
		console.log("Meow");
	}
};
```

The second is through the object's _prototype_:
```
var dog = {};
dog.prototype.bark = function bark() {
	console.log("Meow");
}
```

## The First
The first method is created within the dog object. It is scoped only to the object to which it assigned.

## The Second
The second method is assigned to the dog's prototype. All objects who share dog's prototype, for example objects created using the same constructor, will receive the same method.

## Which Should I Use?
As with everything, it depends.

Javascript creates a new function each time you assign a method directly to an object (or to its constructor function). When you assign a method to an object's prototype, it is created just once and inherited by other objects. Using the prototype approach will generally use less system resources.

When you want multiple objects to have their own methods that can access their own private variables, you will NEED to assign methods to them directly. *At all other times, use the prototype approach!*

## Other things you will now need to find out about:
- What even is a prototype?
- Object literals vs object constructors
- Named vs unnamed functions




