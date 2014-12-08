# PhantomJS

PhantomJS is a headless WebKit with JavaScript API.

*Webkit*: is the layout engine that Chrome, Safari, and a few other browsers use. So basically PhantomJS is a browser, but a headless browser. This means that the rendered web pages are never actually displayed (really nice feature). This may sound weird to you; so you can think of it as a programmable browser for the terminal. 

*Layout Engine*: (also called a web browser engine or rendering engine) is a software component that takes marked up content (such as HTML, image files, etc.) and formatting information (such as CSS, etc.) and displays the formatted content on the screen.


## Why use PhantomJS?

To properly test user stories end to end. To follow on what I said yesterday: it allows you to test your fully rendered DOM which you cannot do with supertest. 

It also is used for other things other than testing (apparently). for a list of use cases see: http://phantomjs.org/buzz.html.

Please note that PhantomJS is not meant to replace a testing framework, but instead work in conjunction with one.


## Cool Features, Functions and Beginnings of Tests

####1. Loading a Page and Render it as a JPG or PNG! To run in your terminal please use `phantomjs test.js`.
	var page = require('webpage').create();
  	page.open('http://natalialkb.github.io/blog/about/', function() {
    	page.render('blog.jpg');
    	phantom.exit();
  	});

####2. Measuring Page load time? Command `phantomjs test.js http://www.google.com`
	var page = require('webpage').create(),
	  system = require('system'),
	  t, address;

	if (system.args.length === 1) {
	  console.log('Usage: loadspeed.js <some URL>');
	  phantom.exit();
	}

	t = Date.now();
	address = system.args[1];
	page.open(address, function(status) {
	  if (status !== 'success') {
	    console.log('FAIL to load the address');
	  } else {
	    t = Date.now() - t;
	    console.log('Loading time ' + t + ' msec');
	  }
	  phantom.exit();
	});

####3. How to access the Dom?

Use the evaluate() function. Note using this there is no way for the code to access any JavaScript objects and variables outside its own page context. An object can be returned from evaluate(), however it is limited to simple objects and can't contain functions or closures.

**Show title of a webpage:**

	var page = require('webpage').create();
	page.open('http://neapolitan-a-la-code.github.io/blog/', function(status) {
	  var title = page.evaluate(function() {
	    return document.title;
	  });
	  console.log('Page title is ' + title);
	  phantom.exit();
	});


**Important to note: phantom.exit() has to appear somewhere in your script**

## Mocha or Karma?

The next step is using a Test Runner like Mocha or Karma and an assertion library like Chai with PhantomJS. 


## Resources

* Really good documentation! http://phantomjs.org/

* Karma Installation: http://karma-runner.github.io/0.12/intro/installation.html

* Karma Config: http://karma-runner.github.io/0.10/intro/configuration.html

* Helping you use Mocha with PhantomJS: http://metaskills.net/mocha-phantomjs/

* Really useful starting point with combing Mocha and PhantomJS using above module: http://code.tutsplus.com/tutorials/testing-javascript-with-phantomjs--net-28243