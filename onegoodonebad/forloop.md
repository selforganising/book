#For Loops

The for loop is the most compact form of looping and includes the following three important parts:

* The loop initialization where we initialize our counter to a starting value. The initialization statement is executed before the loop begins.

* The test statement which will test if the given condition is true or not. If condition is true then code given inside the loop will be executed otherwise loop will come out.

* The iteration statement where you can increase or decrease your counter.

You can put all the three parts in a single line separated by a semicolon.


###Syntax

	for ([initialization]; [condition]; [final-expression]) {
		//do something here
	};


### Bad

	for (var i = 0; i < arr.length; i++) {


This is the most used and most readable version. The biggest disadvantage is this for loop looks up the .length property of the array each time through the loop.


### Good

	var len = arr.length; 
	
	for (var i = 0; i < len; i++) {

This is the optimised version of this loop. Here the length of the array is only looked up once and held in a variable.

However, to notice how much faster this is then the above you would have to run the loop a couple of thousand times.

Please Note: this only works is the length of the array do not change which it is in the loop.



### Resources:

* http://www.openjs.com/articles/for_loop.php

* http://www.sitepoint.com/google-closure-how-not-to-write-javascript/


*Natalia, FAC3* 