# Functions 101

You're not going to get anywhere in computer programming without understanding functions back and front.

### What's in a name?

    // YEAH! I CAN GUESS WHAT THIS DOES
    function multiply (number1, number2) {
      alert(number1 * number2);
    }

This is called 'declaring' the function. We can now use the multiply (x,y) function.

Name your function something SO OBVIOUS that someone doesn't have to go find it to figure it out.

### John Doe

    // meh
    function(title) {
      // code goes here again
      alert(title);
    };

Functions don't have to have names, but that just seems mean. This may be the case for IIFEs (immediately-invoked function expressions).

### Iffy on IIFEs

    // immediately-invoked function expression (IIFE)
    // sometimes necessary
      (function() {
        console.log('Welcome to the Internet. Please follow me.');
      })();

Don't worry, it's just an unnamed function that does something immediately.

### Where NOT to declare functions
    
    if (currentUser) {
      function test() {
        console.log('Nope.');
      }
    }

Don't declare functions inside an 'if' statement. Never. Same for While blocks. Browsers will let you do it, but they all do it differently so only God knows what happens next.

### Be careful with your parameter names

    // bad
    function nope(name, options, arguments) {
      // ...stuff...
    }

    // good
    function yup(name, options, args) {
      // ...stuff...
    }

You cannot use the variable name "arguments" as a parameter. Don't do it, you'll create a black hole and we'll all be goners. Plus your code won't work. It's a restricted word. Use args or literally almost anything else.

*Marc, FAC3*