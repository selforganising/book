# Fun with scope

What is scope?

Scope explains where variables (and functions) are accessible from. Variables (and functions) can have GLOBAL scope, or can have LOCAL scope.
    
      var testscore = 90;

      function display() {
          alert(testscore);
      }
      
      display();
      alert(testscore);
      

_the above example will print "90" in both places_
[http://jsfiddle.net/89mdbt0b/](http://jsfiddle.net/89mdbt0b/)

In this example, the variable testscore is *GLOBAL.*
A global scope means the variable is accessible anywhere in the code.

      function greeting () {
          var saying = "Sup?";
          alert(saying);
      }
        
      greeting(); // will print "Sup?"
      
      alert(saying); //  error

_the above code will write "Sup?" before throwing an error_
[http://jsfiddle.net/v8mshkp3/](http://jsfiddle.net/v8mshkp3/)

In the above example, the variable saying is *LOCAL.*
It is only available within the greeting function.
That's why we get an error on the console.log outside of the function.

Availability cascades downward. If your var declaration is the first line (source), it is Global and accessible everywhere. If it is declared in a function, its only available in that function.
  
     function loudName (firstName) {
    
         function capitalizeName () {
      	    return firstName.toUpperCase();
         }
       	 var capitalized = capitalizeName();
      	 return capitalized;
      }
        
      alert(loudName("Adam")); // Returns "ADAM"
  
_The above example will print "ADAM"_

[http://jsfiddle.net/5b7juw6x/2/](http://jsfiddle.net/5b7juw6x/2/)

In this example, the variable firstName saying is *LOCAL* and effectively declared in the first line.
However, because availability cascades downward, the capitalizeName function can access it w/ no problem.
With nested functions, the inner functions have access to all variables that the parent function does.
      
      function loudName (firstName) {
          var capitalized = capitalizeName();
          return capitalized;
      }
      
      function capitalizeName () {
          return firstName.toUpperCase();
      }
      
      alert(loudName("Adam")); // error


_The above example will not work as written_      [http://jsfiddle.net/dawhwvct/](http://jsfiddle.net/dawhwvct/)

In this example, the variable firstName saying is still *LOCAL* and effectively declared in the first line.
However, because the capitalizeName function is no longer within loudName, it doesn't work.

###Summary
Be aware if your variables (and functions) are GLOBAL or LOCAL. Availability cascades downward

###Next courses

*Scope 102: Common Mistakes: var declarations and block scope*

*Scope 103: Hoisting*

*Scope 201: Closures*
  


*Adam, FAC3* with thanks to robertnyman and dailyjs