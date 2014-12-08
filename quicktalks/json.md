#Introduction to JSON

##Traditional internet

Servers send HTML files at the request of your browser.
They send them in strings and they get converted back into readable HTML files and your browser shows you the good stuff.

##Introducing AJAX

A quicker way to respond to users.

Don't send whole html files. Send small strings in response to user behaviour.

Example: Guardian API

###Introducing to JSON

Ok, so how do we send these smaller bits of information?
We still need to use strings to send. Here JSON can help us.

JSON is the language data is written in so that it can be transferred from server to browser.

It is a string.

We used JSON in our Guardian and BBC Weather API. It looked like this:

    {"coord":{"lon":-0.13,"lat":51.51},"sys":{"type":1,"id":5091,"message":0.0234,"country":"GB","sunrise":1412229817,"sunset":1412271346},"weather":[{"id":800,"main":"Clear","description":"Sky is Clear","icon":"01d"}],"base":"cmc stations","main":{"temp":290.54,"pressure":1029,"humidity":72,"temp_min":289.15,"temp_max":291.65},"wind":{"speed":2.1,"deg":70},"clouds":{"all":0},"dt":1412246542,"id":2643743,"name":"London","cod":200}

##How do you use JSON?

####Writing an API
You don't write stuff in JSON. You convert your code (Javascript, C++, whatever) to JSON.If you're writing an API in Javascript then you can convert your object to JSON using:JSON.stringify()

See it in action:

    1. JSON.stringify({
    2.     name: "Jim Cowart",
    3.     country: "Jimbabwe"
    4. });
    5. // produces: "{"name":"Jim Cowart","country":"Jimbabwe"}"

####Using an API
If you want to use someone else's JSON (or your own) in javascript you can use:

JSON.parse.First assign your JSON to a variable like so:

    var text = '{ "employees" : [' +
    '{ "firstName":"John" , "lastName":"Doe" },' +
    '{ "firstName":"Anna" , "lastName":"Smith" },' +
    '{ "firstName":"Peter" , "lastName":"Jones" } ]}';

Then parse that variable, in this case "text", using JSON.parse(), like so:

var obj = JSON.parse(text);

###References:

Dan's notes from Week 2: http://book.selforganising.org/week2/apis.html

w3 schools on parse: http://www.w3schools.com/js/js_json.asp

Freshly Brewed Code on stringify: http://freshbrewedcode.com/jimcowart/2013/01/29/what-you-might-not-know-about-json-stringify/

Dan's mind: ask Dan.

*Ben, FAC3*

