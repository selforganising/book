#Named & Anonymous Functions


##Why should you use anonymous functions?

1) code brevity <br>
2) scope management - nonymous functions can be used to create temporary/private scope <br>
3) Anonymous function are often handy in closures and recursions. (A whole other talk topic.) <br>

##Why shouldn't you use anonymous functions?

1) Can be more difficult to debug <br>
2) They cannot be reused <br>
3) Harder to test <br>
4) Do not describe the role of the function <br> 
5) Can make code appear to lack structure and make it more difficult to read <br>


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

//In this example,, foo, bar and baz are not accesible outside of the anonymous function, so they will not console.log.

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

//To allow access to a variable or function, we need to expose it to the global ‘window’ object.

(function(){
  var foo = 'Hello';
  var bar = 'World!'
  
  function baz(){
      return foo + ' ' + bar;
  }

  window.baz = baz; //Assign 'baz' to the global variable 'baz'...
})();

console.log(baz()); //...and now this works.

//It's important to note that these still won't work: 
console.log(foo);
console.log(bar);


If you create an anonymous function and assign it to a variable immediately when the function is 
defined then the function can be referenced via that variable in the same way as it could be if you 
gave the function that name when you created it. The difference is that when you assign an anonymous 
function to a variable the variable only points to the function from that point in your code onward 
and you can assign a different value to the variable at any time to replace the function. 


// anonymous function assigned to a variable cannot be called before the variable is initialized
fnAnonymous(); // undefined

var fnAnonymous = function(){

    alert("hi");

};

fnAnonymous(); //hi

// a named function can be accessed anywhere as long as it is within the same scope that the function is created

fnNamed(); // hi

function fnNamed(){
	alert("hi");

};

fnNamed(); //hi


