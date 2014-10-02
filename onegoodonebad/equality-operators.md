###Equality Operators

##What do they do ?

"JavaScript has two sets of equality operators: === and !==, and their evil twins == and !=. The good ones work the way you would expect. If the two operands are of the same type and have the same value, then === produces true and !== produces false. The evil twins do the right thing when the operands are of the same type, but if they are of different types, they attempt to coerce the values. the rules by which they do that are complicated and unmemorable. These are some of the interesting cases:" - Doug Crockford

* Using the == operator (Equality)

    true == 1; //true, because 'true' is converted to 1 and then compared 

    "2" == 2;  //true, because "2" is converted to 2 and then compared


* Using the === operator (Identity)
  
    true === 1; //false 

    "2" === 2;  //false

##What's going on?

This is because the equality operator == does type coercion, meaning that the interpreter implicitly tries to convert the values before comparing.
On the other hand, the identity operator === does not do type coercion, and thus does not convert the values when comparing.

*Max, FAC3*