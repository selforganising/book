# JavaScript Idiomatic Expressions With && and ||

You see these idiomatic expressions in JavaScript frameworks and libraries. Let’s start off with a couple of basic examples:

### Example 1: Basic “short circuting” with || (Logical OR)

To set default values, instead of this:

    function documentTitle(theTitle)
    if (!theTitle) {
    theTitle  = "Untitled Document";
    }
    }

Use this:

    function documentTitle(theTitle)
    theTitle  = theTitle || "Untitled Document";
    }

Explanation:

— The || operator first evaluates the expression on the left, if it is truthy, it returns that value. If it is falsy, it evaluates and returns the value of the right operand (the expression on the right).

— If theTitle variable is falsy, the expression on the right will be returned and assigned to the variable. On the other hand, if theTitle is truthy, its value will be returned and assigned to the variable.

##### JavaScript Falsy Values: null, false, 0 undefined, NaN, and “” (this last item is an empty string).
##### JavaScript Truthy Values: Anything other than the falsy values.

### Example 2: Basic short circuting with && (Logical AND)

Instead of this:

    function isAdult(age) {
    if (age && age > 17) {
    return true;
    }
    else {
    return false;
    }
    }

Use this:

    function isAdult(age) {
    return age && age > 17 ;
    }

Explanation:
— The && operator first evaluates the expression on the left. If it is falsy, false is returned; it does not bother to evaluate the right operand.
— If the the first expression is truthy, also evaluate the right operand (the expression on the right) and return the result.

Example 3:
Instead of this:

    if (userName) {
    logIn (userName);
    }
    else {
    signUp ();
    }

Use this:

     userName && logIn (userName) || signUp ();

Explanation:
— If userName is truthy, then call the logIn function with userName as the parameter.
— If userName is falsy, call the signUp function

Example 4:
Instead of this:

    var userID;
    if (userName && userName.loggedIn) {
    userID = userName.id;
    }
    else {
    userID = null;
    }

Use this:

    var userID = userName && userName.loggedIn && userName.id

Explanation:
— If userName is truthy, call userName.loggedIn and check if it is truthy; if it is truthy, then get the id from userName.
— If userName is falsy, return null.
