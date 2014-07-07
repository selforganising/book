# Arrays in JavaScript

Arrays in JavaScript are just lists of objects.

    var foo = ['a', 'b', 'c'];

The items in an array can be any kind of object and they do not all have to be the same.

    var bar = ['x', 42];

And arrays can be nested:

    var baz = [[1 ,2], [3, 4]];

Or can contain compound objects:

    var qux = [{name: jim}, {name: sam}];

Items can be added to the end of a list:

    var foo = [];
    foo.push(bar);

Or removed:

    foo.pop();

The last element is returned, so you can use it;

    var baz = foo.pop();

Items can also be added to the front of a list:

    foo.unshift(bar);

Or removed:

    baz = foo.shift();

You can return any item in a list by its index:

    foo[0]

Or assign a new value:

    foo[1] = 'x';

Every array has a length:

    foo.length;

And since ECMAScript 5 came out, you can iterate through a list with a callback:

    foo.forEach(function(item){
        // do something
    });

You can do more with arrays. Take a look at the [documenentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).



