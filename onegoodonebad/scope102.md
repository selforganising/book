# Scope 102: variable declaration errors and block scope

*How should we declare variables?*

It is common to declare variables in a cluster. When multiple variables are declared, you can skip the 'var'. Cool, I'm a pro, right?
    
      var a = 90,
          b = 91,
          c = 92;

But is this a good idea? What happens if we miss a comma?

    // beginning of code
      function example() {
        var a = 90
            b = 91,
            c = 92;
      }

These are all local, right? Wrong! B and C are actually global. When you fail to declare var in JS, it becomes global by default. Which might mess up something elsewhere. The Google style guide recommends using a var statement on each line to avoid this problem.

          var a = 90;
          var b = 91;
          var c = 92;
          function example() {
            var d = 90;
            var e = 91;
            var f = 92;
          }
  
*The first rule of block scope is...*

There is no such thing as block scope. A declared variable is not defined to its block (FOR loop, IF THEN, etc)

      
     function foo() {
       // Do not do this
      for (var j = 0; j < 5; j++) {
        var k = 1;
        // Do stuff with `k`
      }
    }

In the above example, the variable a is available throughout the example function, regardless of blocks. Instead, do it like this:

      function bar() {
        var i, a;
        for (i = 0; i < 3; i++) {
          a = 1;
          // Do stuff with `a`
        }
      }

This makes the scope of i and a much more obvious.




###Summary###
Use a 'var' declaration if you are creating a new variable. Less scope for error with commas etc.

There is no such thing as block scope in JS.

###Next courses###
*Scope 103: Hoisting*

*Scope 201: Closures*
  


*Adam, FAC3* with thanks to dailyjs