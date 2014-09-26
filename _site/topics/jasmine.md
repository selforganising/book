# Jasmine

A [really simple demo](http://sofer.github.io/jasmine-demo/) (and here is [the repo](https://github.com/sofer/jasmine-demo)).

## A test suite

A series of tests

`describe(str, callback)`

## A spec

An individual test

`it(str, callback)`

## An expectation

Takes an actual value to be tested

`expect(actual)`

## A matcher

Takes an expected value and is chained with an expectation (and sometimes also with `not`).

    expect(actual).toBe(expected)
    expect(actual).not.toBe(expected)

They include `toBe`, `toEqual`, `toMatch`, `toBeDefined`, `toBeUndefined`, `toBeNull`, `toBeTruthy`, `toBeFalsy`, `toContain`, `toBeLessThan`, `toBeGreaterThan`, `toBeCloseTo`, `toThrow` and you can make your own custom matchers, too.

An example:

    describe("A suite", function() {
        it("contains spec with an expectation", function() {
            expect(true).toBe(true);
        });
    });


A suite may contain many specs. A spec may contain many expectations. 

You may want to add some code before you runs the specs and you may also want setup code specific to each spec:

    describe("A suite is just a function", function() {   
        var a;    
        it("and so is a spec", function() {     
            a = true;      
            expect(a).toBe(true);
        }); 
    });

##Setup and teardown

If you want the same code run for each spec in a suite before and after each spec, you can use:

`beforeEach(callback)` and `afterEach(callback)`.

##Disabling suites and specs

`xdescribe()` causes a suite to be ignored and `xit` causes a spec to be marked as `pending`. Useful if your suites or specs are not just failing but causing your code to break.

##Spies

We won't go into detail here, but they allow your tests to track calls to any function over the course of a test, allowing you to test not just output values, but also the course of execution in your code.

`spyOn()`, `toHaveBeenCalled()`,  `toHaveBeenCalledWith(value)`

##Installation

to get Jasmine running, you can clone the [really simple demo](https://github.com/sofer/jasmine-demo)) or you can follow the [installation instructions](https://github.com/pivotal/jasmine).

If you follow these instructions, you will get a bunch of files in your *jasmine* folder.

###SpecRunner.html

This is the file you should navigate to in your browser. It contains the Jasmine code as well as *source* files, that contain some dummy JavaScript code, and the *spec* files, that contain some dummy tests.

Take a look at *spec/PlayerSpec.js* and *src/Player.js*.

You can run *SpecTunner.html* by starting `http-server` and navigating to it in your browser (`npm http-server` if you have not got it installed).

Note that normally you would expect the *src* files to sit in your main application directory, not inside the jasmine directory.

If you are feeling adventurous, you may also want to give [karma-jasmine](https://github.com/karma-runner/karma-jasmine) a go. See [Karma](http://karma-runner.github.io/0.12/index.html).


