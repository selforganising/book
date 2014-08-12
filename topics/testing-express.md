# Testing an Express application

Read [Testing](topics/testing) first.

### Acceptance tests

Remember that in pseudo-code, an acceptance test might look something like this:

    describe('When a User goes to the home page'):
        it('should actually exist')
        it('should display the message, "Hello, Camden Town"')

### package.json

Add mocha and supertest as dependencies in `package.json` and run `npm install`.

### test/test.js

Create a test folder and add a `test.js` file.

### test.js

Create a test file as follows:

    var express = require('express'),
        request = require('supertest'),
        app = require('../app.js');

    request = request(app);

    describe('When a user goes to the home page', function() {
        it("should return status code 200 OK", function(done) {
            request.get('/')
                .expect(200, done);
        });

        it("should return some text referencing 'Camden Town'", function(done) {
            request.get('/')
                .expect(/Camden Town/, done);
        });
    });

And run `mocha`.