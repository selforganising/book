# Functions in JavaScript

In JavaScript, functions are just objects. They can be manipulated like any other object. This is a powerful property of functions in JavaScript, not widely available in other languages.

Functions that are objects can be created on-the-fly as code is running, can be assigned to variables, and can be passed as arguments.

Functions can also contain their own variables and other functions. In other words, they can have *properties* and *methods*, just like any other object. 

### A function declaration

    function foo(bar) {
      // code goes here
    }

This is a function named `foo` that takes an argument `bar`. This is the conventional way of creating a function that can be used elsewhere in your code. It is similar to the way functions are created in many other programming languages (Note: no trailing `;` is needed at the end of the declaration).

### An anonymous function

    function(bar) {
      // code goes here again
    };

This is a function with no name (note the trailing `;`).

### A function expression

    var foo = function(bar) {
      // code goes here yet again
    };

Here, an anonymous function has been assigned to a variable for later re-use. It is equivalent to the function declaration above. Although it is partly a matter of taste, use function expressions instead of function declarations. It will remind you that *functions are just objects* and do not require any special syntax. 

### A named function expression

    var foo = function foo(bar) {
      // code goes here one more time
    };

This is just a function expression, but also giving the function a name (rather than just assigning it to a variable), can be helpful for debugging. If you cannot work out what your code is doing, add names to your functions.

### An immediate function

    (function() {
      // code... again
    }());

This function executes immediately.

You can also write:

    (function() {
      // code, for the last time
    })();

Note the slightly different order of the parentheses.

    

