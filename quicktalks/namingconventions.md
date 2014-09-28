# Naming Conventions

## Why implement naming conventions?

*Order *
Particularly important when moving from local to global and personal to collaborative
*Sustainability*
Maintaining a project, particularly as the scale increases
*Speed and Efficiency*
Code is recongnisable and easy to dive into
---
## Naming Conventions in Javascript (According to Airbnb)

###useCamelCase for functions objects and instances**

```
var thisIsMyObject = { };
```

```
function thisIsMyFunction( ) { }
```

```
var user = new User( {
name: 'Bob Parr'
} );
```

###Name your functions

*Be descriptive with your naming.*

```
// bad
var log = function( msg ) {
	console.log( msg );
};
```

```
// good
var log = function log( msg ) {
	console.log( msg );
};
```

*Avoid single letter names.*

```
// bad
function q( ) {
// ...stuff...
}
```

```
// good
function query( ) {
// ..stuff..
}
```

###UsePascalCase for constructors and classes

```
function User( options ) {
	this.name = options.name;
}
```
```
var good = new User( {
	name: 'yup'
} );
```

###Private Properties - use a leading underscore

"A private property is a property that is only accessible to member functions of instances of the same class."

```
this._firstName = 'Panda';
```

###When saving a reference to this use _this.

function( ) {
var _this = this;
return function( ) {
console.log( _this );
};
}