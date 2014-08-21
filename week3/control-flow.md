#Flow of control in Node

Node.js makes use of the JavaScript [event loop](http://en.wikipedia.org/wiki/Event_loop) to allow multiple flows of control in your code.

Functions like `fs.readFile()` and `http.createServer()` run as separate processes outside the main flow of the program.

This has the great advantage of allowing several processes to run simultaneously without any one process blocking the progress of any of the others.

This is particular useful for multi-user network applications (like a web server).

But it does mean that care has to be taken [not to make assumptions](http://blog.sofer.com/tech/2011/06/07/nodejs-confusion.html) about the order in which different blocks of code are going to execute.

Here is an example:

    var fs = require('fs'),
        file = 'stuff.txt',
        output;
 
    fs.readFile(file, function(err, data) {
        output = data.toString();   // 'some stuff' 
        console.log('Here: ' + output);
    })    

    console.log('There: ' + output);

    > There: undefined
    > Here: some stuff

The call to `fs.readFile` creates a new flow of control in the code: the callback will execute after the file have been opened. Meanwhile the original control flow continues and reaches a point where an undefined `output` is printed to the screen. Eventually, the file is opened and the file contents are assigned to the `output` variable, which is then printed to the screen.