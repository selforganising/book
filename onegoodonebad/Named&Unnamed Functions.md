#Named & Anonymous Functions


##What's good about anonymous functions?

1) Code brevity <br>
2) Scope management - anonymous functions can be used to create temporary/private scope <br>
3) Anonymous functions are often handy within the context of closures and recursions. (A whole other talk topic.) <br>

##What's not so good about anonymous functions?

1) Can be more difficult to debug <br>
2) They cannot be reused <br>
3) Harder to test <br>
4) Do not describe the role of the function <br> 
5) Can make code appear to lack structure and make it more difficult to read <br>
6) Named functions appear on your stack trace (a report of the active stack frames at a certain point in time during the execution of a program).


##Simple example of named vs. annonymous functions

_//Named_ <br>

	var foo = 'Hello';
	    var bar = 'World!';

	function baz(){
	    return foo  + ' ' + bar;
	}

	console.log(baz());

_//Anonymous_ <br>

	(function(){
   	    console.log('Hello World!');
	})();

The final two parentheses cause everything contained in the preceding parentheses to be executed immediately. 
As JavaScript has function level scoping, all variables and functions defined within the anonymous function aren’t available to the code outside of it.

_//In this example,, foo, bar and baz are not accesible outside of the anonymous function, so they will not console.log._ <br>

	(function(){
  	   var foo = 'Hello';
   	   var bar = 'World!'
  
  	function baz(){
      	   return foo + ' ' + bar;
  	}
	})();

_//These all throw exceptions:_ <br>

	console.log(foo);
 	console.log(bar);
	console.log(baz());

_//To allow access to a variable or function, you could refer it to a global object._ <br>
	
	var yoyo = {};
	
	(function(){
  	   var foo = 'Hello';
  	   var bar = 'World!'
  
   	function baz(){
      	   return foo + ' ' + bar;
  	}

	   yoyo.baz = baz; //Assign 'baz' to the global variable 'baz'...
	})();

	console.log(baz()); //...and now this works.

_//It's important to note that these still won't work:_ <br> 

	console.log(foo);
	console.log(bar);

####Finally: 

// An anonymous function assigned to a variable cannot be called before the variable is initialized <br>

	var y = function () {
    	   console.log('y');
	};
// But a named function can be accessed anywhere as long as it is within the same scope that the function is created <br>

	x(); // Works even though it's above the declaration
	function x() {
    	   console.log('x');
	}

####I.e. an anonymous function is defined at run-time, whereas a named function is processed when execution enters the context in which it appears, before any step-by-step code is executed. 

_Why does this work? Aren't expressions always excuted from top to bottom??

Function declarations and variable declarations are always moved (hoisted) invisibly to the top of their containing scope by the JavaScript interpreter: 


	functionTwo();              ---------------      function functionTwo() {
	                            | is actually |      };
	function functionTwo() {    | interpreted |-->       
	}                           |    like     |      functionTwo();
