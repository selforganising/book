# Javascript - Semicolons


### What is the feature?

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

### When to not use it?



### Alternative implementations and antipatterns

