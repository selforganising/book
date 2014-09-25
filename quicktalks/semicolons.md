# Javascript - Semicolons


### What is the feature?

Inserting a semicolon finishes the statement you are working on in Javascript. It tells the browser you have finished a command. 



### How would you use it?

		// bad
	(function() {
	  var name = 'Skywalker'
	  return name
	})()
	
	// good
	(function() {
	  var name = 'Skywalker';
	  return name;
	})();

	// good (guards against the function becoming an argument when two files with IIFEs are concatenated)
	;(function() {
	  var name = 'Skywalker';
	  return name;
	})();



### Why would you use it?

 Javascript  interprets your code itself if you do not have any semicolons, which can mess up the code and the way you want it to look like. Semicolons are optional BUT it is highly recommended to insert them. 

 The basic way the script interpreter works is that if there is no semicolon, it will continue scanning the next line, and if it sees something at the start of it that cannot possibly be a part of the command on the previous line, then it will assume you forgot to insert a semicolon, and it will effectively put one there for you. If it can be part of the last command, it will assume it is part of the last command. Operators and property references are an obvious example of what will be allowed to continue the last command. 



### When to not use it?

Here are examples when to NOT use a semicolon:

![When not to use a semicolon](/../images/semicolonpic.png "When not to use a semicolon")




### Alternative implementations and antipatterns

There is no alternative to semicolons and you could just stop using them and do linebreaks instead. That would be an antipatterns which works but its not recommended and is bad practice. 
<strong>DO USE SEMICOLONS, GUYS!</strong> 

*Subhan, FAC3*