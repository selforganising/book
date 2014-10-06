JS can convert numbers to strings...

	var x = 5 + 7;       // x.valueOf() is 12,  typeof x is a number

	var x = 5 + "7";     // x.valueOf() is 57,  typeof x is a string
	var x = "5" + 7;     // x.valueOf() is 57,  typeof x is a string

	var x = 5 - 7;       // x.valueOf() is -2,  typeof x is a number
	var x = 5 - "7";     // x.valueOf() is -2,  typeof x is a number
	var x = "5" - 7;     // x.valueOf() is -2,  typeof x is a number
	var x = 5 - "x";     // x.valueOf() is NaN, typeof x is a number

Substracting a string from a string will not return an error, it returns NaN.

	"Hello" - "Dolly" // returns NaN

If-statements can automatically convert things to booleans:

	var element = document.getElementById("someId");
	if (element) {
  		// do something
	}

Here element:
 an object --> true
 null --> false





Extra Reading
* http://united-coders.com/matthias-reuter/all-about-types-part-2/