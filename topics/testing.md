# Testing

We are going to introduce testing right from the start of this course and we are going to use an approach to testing that fits in well with the agile approach and with the story-based project management tool that we are using.

Before we write any other software, we are going to write test code to test the *expected behaviour* of our software. This approach is known as ***behaviour-driven development***, or ***BDD***.

## BDD

In BDD, we start with ***acceptance criteria***. These are the criteria that a non-technical user can use to judge whether an application works as intended. These criteria should map to the *user stories* as defined in the [sprint planning](topics/planning) sessions.

### User stories

Stories include a *scenario* and an *outcome*. An example might be:

    For a User, the home page should display the text, "Hello, Camden Town"

Stories should generally be of this *"For...should..."* form.

These *acceptance criteria*, expressed as *user stories* are then turned into ***acceptance tests***.

###Acceptance tests

Acceptance tests are code that tests the outcome of a given user story. If a user story is carefully composed, then translating it into code is relatively simple.

In pseudo-code, a test might look something like this:

    describe('For a User, the home page'):
        it('should actually exist')
        it('should display the message, "Hello, Camden Town"')

The `describe` block defines some scenario and each of the enclosed `it` blocks  describe some desired outcome.

### Mocha

For testing we are going to use [Mocha](http://visionmedia.github.io/mocha/), a JavaScript testing library. 

Install Mocha as follows:

    npm install -g mocha

In a new directory, create a file `test.js` and add the following:

    var assert = require('assert');

    describe('The number one', function() {

        it('should equal 1', function() {
            assert.equal(1, 1);
        });

        it('should not equal 2', function() {
            assert.notEqual(1, 2);
        });

    });

Then run:

    mocha

And your tests should pass, like this:

    The number one
      ✓ should equal 1
      ✓ should not equal 2
    
    2 passing

### Supertest

As well as *mocha*, we are going to use [*Supertest*](https://github.com/visionmedia/supertest), a JavaScript library for testing HTTP servers. This will allow us to test actual web pages, making GET and POST requests and checking the response.

Using Supertest, we can easily map user stories to acceptance tests for web applications.

A test script might look like this:

    var request = require('supertest');
    request = request('http://foundersandcoders.org/');

    describe('For a user, the home page', function() {

        it("should return status code 200 OK", function(done) {
            request.get('/')
                .expect(200, done);
        });

        it("should return some text referencing 'Camden'", function(done) {
            request.get('/')
                .expect(/Camden/, done);
        });

    });

And these should pass as follows:

    For a user, the home page
      ✓ should return status code 200 OK (207ms)
      ✓ should return some text referencing 'Camden' (243ms)

    2 passing (459ms)





