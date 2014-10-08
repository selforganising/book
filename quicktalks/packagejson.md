# package.json

### What is it?

Package.json is a standardised file that holds various metadata relevant to the project.

**Metadata**: a set of data that describes and gives information about other data.


### Why use it?

For developers the most important use is the dev dependencies. On your command line use `npm install` and if there is a package.json with dependencies listed then it will install them all. Since some projects have many dependancies this is a huge time saver.

**Important note**: package.json is for all backend javascript/node metadata. For front end javascript you can make a bower.json (for another talk).


| **Advantages**                                  | **Disadvantages**                          |
| ------------------------------------------------|--------------------------------------------|
| Easily find and install dependancies            | None (that I can find)                     |
| Easily install correct version for dependancies | It is just common practise                 |
| Great way to run tests (ask Besart/Testers)     |                                            |
| Crucial to publish on npm or equivalent         |                                            |


### How to use it?

1.	npm init (creates package.json)
2.	Answer all the questions as detailed as you want to be.
3.  Add dependancies and scripts (optional but recommended).

### Resources:

* Interactive package.Json: http://browsenpm.org/package.json

* Npm guide to package.json: https://www.npmjs.org/doc/files/package.json.html
