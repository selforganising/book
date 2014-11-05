# Week 8: Assignment 1

## Re-write a TodoMVC app

To start off this week, you are not going to write an AngularJS app, but instead you are going to re-write an existing app. This will act as hapi revision as well as an introduction to AngularJS. You will also get a chance to look at Bower, as well as Jasmine and Karma.

### The task

Design, test and complete a hapi-based REST API for an existing Todo app. We will take as our starting point the complete [Angular.js Todo app](http://todomvc.com/architecture-examples/angularjs/#/) at [TodoMVC](http://todomvc.com/).

The steps will be as follows:

1. Clone [TodoMVC](https://github.com/tastejs/todomvc);    
1.`npm install -g [bower](http://bower.io/)`;    
1. Navigate to `architecture-examples/angularjs` and `bower install`;
1. Take a quick look at `bower.json` and note its similarity to node's `package.json`. This file ensures that all the necessary files for this application are stored in `bower_components` in the current folder;
1. `npm install -g http-server`, navigate to [http://localhost:8080/](http://localhost:8080/) or your local equivalent and have a play;
1. Go back to your chosen architecture example, navigate to `test/`, and type `npm install`;
1. Take a look now at `package.json` and at `node_modules`. Again, all the dependencies have been downloaded into the current folder;
1. `npm test`; 
1. If you are on Nitrous.IO, you will need to launch a preview and manually add port `9876`, otherwise on your own laptop a browser should launch automatically;
1. While the test watcher is running, in your editor go to `js/app.js`, add a carriage return (or other inconsequential character) and save. Go back to the terminal window and watch the tests running. They should all pass;
1. `Ctrl-c` to stop the tests and go and inspect `test/unit/todoCtrlSpec.js`. These tests are not easy to understand at first glance, but they are using Jasmine as well as the Angular test tunner, [Karma](http://karma-runner.github.io/0.12/index.html).

At this point, you will have something of a feel for how a well-constructed client-side web application is put together, with the use of package managers like Bower and npm, and a test runner like Karma. Take a look, also, at the application files, in order to get a feel for AngularJS. Note the `ng-` attributes in *index.html*, the main `angular.module` declaration in *js/app.js* and the main controller at *js/controllers/todoCtrl.js*. We are now going to return to the next phase of this exercise.

1. In your editor, navigate to `js/services/todoStorage.js`;
1. You will notice that there are `get` and `put` methods that are getting data to and from local storage. The task now is to replace these methods with new methods that access a REST API that you are now going to build;
1. Keep the `get` and `put` methods, but comment out the the lines that make up the body of the methods;
1. Now run the tests again using `npm test` and note that your tests are all now failing;
1. It is now your job to build a lightweight REST API using hapi to get and put the Todos, instead of the local storage on your browser, and to re-write the `get` and `put` methods to use the API;
1. If you are feeling adventurous, you can re-write `get` and `put`, so that they use both local and remote storage, so if you are offline your app will continue to function and when you go back online the local and remote data will be synched. This is a tricky problem, so it is optional, but it is a technique used by countless mobile apps.

You should try to complete this task in time for the code reviews on Tuesday afternoon.