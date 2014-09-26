# Frontend build tools

Build tools can be a bit confusing and you may choose not to use them at all, but once you get familiar with them, they can make your life as a developer a lot easier. 

The other nice thing about build tools is that if you are using a framework like, say, Angular.js for the first time, build tools will give you a skeleton to work from very quickly.

These tools fall into three broad categories.

##Task runners

Once you start using tests and using CSS preprocessors, you are going to be continually re-building and testing your project. This can quickly become a bit tedious to do manually. This is where task runners come in. They allow you to automate these sorts of tasks.

The most widely-used task runner is probably [Grunt](http://gruntjs.com/), but we are going to use [Gulp](http://gulpjs.com/) ("the streaming build system").

##Package managers

We have already used *npm*, You will have noticed that whenever you run *npm*, all the software you need for a new package is installed for you without you having to check dependencies.

[Bower](http://bower.io/) does something similar for your frontend code. 

##Scaffolding tools

You may have noticed that when building your websites you have had to include several libraries, like *Bootstrap*, *jQuery* and perhaps *Modernizr*.

[Yeoman](http://yeoman.io/learning/) was developed to make it easier to start a new project with all the libraries and tools that you are likely to want to use. 

Yeoman uses *generators* (configuration files) to create a scaffold, run relevant tasks using a task runner, and  install any required frontend packages.


Start with Gulp. Watch [Joe Maddalone's introduction to gulp.js](http://youtu.be/lRyRuQdjAww) to get a flavour. 

But also See [Paul Irish's talk at Google I/O 2012](http://youtu.be/Mk-tFn2Ix6g) for a more in-depth overview.


