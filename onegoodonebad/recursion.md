## Inception 2: Recursion!

Recursion is when you call a function inside itself. It is potentially very powerful (and potentially very confusing). 

Take for example the following loop:

	var i;

	for (i = 0; i < 10; i += 1) {
	
		console.log(i);

	}


The loop will print all the values 0 to 9. To write this recursively, we need to write a NAMED function:

	function printer (x) { //Define the function with a NAME!
		
		if (x > 9) {		//If the parameter is above 9, stop the press!
			return;
		}
		
		console.log(x);		//Print the parameter
		
		printer(x+1);		//Call the function again passing argument x+1 to parameter x. 
	}

	printer(0); //Call the function!

Both methods are good and with a task this simple, it's hard to see the point of using recursion. It is a powerful tool for building complex functions!
