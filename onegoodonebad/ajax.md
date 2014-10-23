# Jquery vs VanillaJS

What is VanillaJS? If you are not sure, please see first resource.

# BAD

	$.ajax({
	    type: "GET",
	    cache: false,
	    dataType: "JSON",
	    url: "yourURL",
	    success: function (data) {
	        // do something with your data
	    },
	    error: function (errorT) {
	        console.log(errorT);
	    }
	});

# GOOD

	function fetchJSONFile(path, callback) {
    	var httpRequest = new XMLHttpRequest();
    	httpRequest.onreadystatechange = function() {
        	if (httpRequest.readyState === 4) {
            	if (httpRequest.status === 200) {
                	var data = JSON.parse(httpRequest.responseText);
                	if (callback) callback(data);
            	}
        	}
    	};
    	httpRequest.open('GET', "yourURL");
    	httpRequest.send();
	}

	// this requests the file and executes a callback with the parsed result once
	//   it is available
	fetchJSONFile("yourURL", function(data){
   		// do something with your data
    	console.log(data);
	});


### Why use Jquery?

| **Advantages**                           | **Disadvantages**                           |
| -----------------------------------------|---------------------------------------------|
| Makes javascript easy                    | Slow - VanillaJS ALWAYS faster              |
| Large library (also disadvantage)        | Possibility of deskilling                   |
| Great documentation                      | Doesn't do anything you can't do without it |
| Makes DOM manipulation and AJAX painless | ...Sloooowwww...                        |


### When not to use Jquery

* You learn much more doing things without it then with.

* If page loading time means something.

* If it matters whether your code is lightweight.

### When to use it?

* If you are in a rush.

* If you don't care about page loading time.


### Resources:

* Vanilla JS: http://vanilla-js.com/

* Step by Step guide to non-jquery Ajax: http://www.webstepbook.com/supplements-2ed/slides/chapter12-ajax-xml-json.shtml#slide1

* explain about all ajax prototype options are: http://api.prototypejs.org/ajax/

* Why was JQUERY so widely used? Good History lesson: http://www.sitepoint.com/do-you-really-need-jquery/

* Alternative examples for jquery: http://youmightnotneedjquery.com/

### Extra:

* DomParser: http://krasimirtsonev.com/blog/article/Convert-HTML-string-to-DOM-element

* childNode: http://www.w3schools.com/dom/prop_element_childnodes.asp

* More on childNode: http://stackoverflow.com/questions/19862693/how-childnode-works
