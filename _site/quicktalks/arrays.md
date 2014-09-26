# ARRAYS

### What?
We use ARRAYS to store multiple values in a single variable.
They are *special* objects. Using typeof will return "object".


JavaScript does not support associative arrays = does not support arrays with named indexes instead of numbers.

["firstName"] 	//bad
[0] 			//good


	var person = new Array()
	person["firstName"] = "John";
	person["lastName"] = "Doe";
	person["age"] = 46;

If you try person["firstName"] it returns "John" but person[0] will return "undefined". If you want an associative array, create an object.

You should use objects when you want the element names to be strings.
You should use arrays when you want the element names to be sequential numbers.

Then, you can use numbers to access the elements included in the array, starting with [0]

We love them because they have built in properties: 

.sort()
.length()
.pop()
.push()
.join()
.slice()
.concat()
.reverse()



--

###Best Practice

Use literal syntax:

	//bad
	var items = new Array();

	//good
	var items = [];

Avoid using "new" if possible. It complicates your code: 

	var points = new Array(40, 100);  // Creates an array with two elements (40 and 100)

	var points = new Array(40);       // Creates an array with 40 undefined elements !!!!!

Simplicity, readability and execution speed.

Give square brackets a chance, " [] " is the same as " new Array() "

Looks so fresh and so clean. 


--

The "length" of the array is the number of elements it has. 
You can use .length to add a new element but you should NOT do this if you do not know the length:

	var someStack = [];

	//bad
	someStack[someStack.length] = "boom";

	//good
	someStack.push('boom');

If you know the length... well do you really know the length? If you think you know the number of elements but get it wrong it will create holes in your array. Which will be frowned upon. So don't do it.

--

When you need to copy an array:

	var len = items.length,
    itemsCopy = [],
    i;

	// bad
	for (i = 0; i < len; i++) {
	itemsCopy[i] = items[i];
	}

	// good
	itemsCopy = items.slice();



You can also use .slice() to convert an array-like object to an array:

	function trigger() {
 	 var args = Array.prototype.slice.call(arguments);
 	 ...
	}

--

##NOT IN AIRBNB GUIDE

As these are *special* objects they for-in loops do not do what you might expect. So use normal for loops. 

If arrays are *special* objects how will I know if it is an array?
--> Create your own function: 

	function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
}

*Emma, FAC3*