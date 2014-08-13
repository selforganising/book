# Behaviour-driven development with an Express application

Read [Testing](topics/testing) first.

### Acceptance tests

Remember that in pseudo-code, an acceptance test might look something like this:

    describe('When a User goes to the home page'):
        it('should actually exist')
        it('should display the message, "Hello, Camden Town"')

### Install Mocha

    npm install -g mocha

### Create a simple express app

    express bdd-demo

Then, create a very simple app.js file:

    var express = require('express'),
        path = require('path');
        app = express();

    app.get('/', function(req, res) {
        res.send('Hello, Camden Town');
    });

    module.exports = app;

### package.json

Add supertest as dependencies in `package.json` and run `npm install`.

    {
      "name": "bdd-express-demo",
      "version": "0.0.1",
      "private": true,
      "scripts": {
        "start": "node ./bin/www"
      },
      "dependencies": {
        "express": "~4.2.0",
        "debug": "~0.7.4",
        "supertest": "*"
      }
    }

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