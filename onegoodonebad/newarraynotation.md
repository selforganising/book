#Good – Array Literal Notation#
var a = [‘1A’,’2B’];

#Bad – Array Constructor Notation#
var a = new Array();
a[0] =  “1A”;
a[1] = “2B”;

Reason #1:
By creating new array, you run the risk of creating a variable called “Array”, which can  then overwrite your initial definition of your array. The odds of this are unlikely but this is one fore-seeable outcome which can be easily avoided by creating arrays differently.


Reason #2

var a = new Array(1,2,3,4,5);
a[0] // returns 1
a.length // returns 5

var a = new Array(10);
a[0] // returns undefined
a.length // returns 10, because of reasons.

However with only on integer to the constructor notation, this will create an array with a length of 10, rather than with the first input as 10. This is confusing and misleading.


#Good – Implicit Array Declation#

A third option for creating arrays, is to use a javascript method such as string.split

var alpha = "I-learn-JavaScript";
var beta = beta.split("-");

so 

var beta = [“I”, “learn”, “JavaScript]



Another easily made mistake with brackets can 


Sources: 

https://coderwall.com/p/h4xm0w
