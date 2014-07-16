B# Let's build a map

Mike Bostock's [great tutorial on D3](http://bost.ocks.org/mike/map/) contains the following chunk of code which display a small map of the British Isles.

    d3.json("uk.json", function(error, uk) {
       if (error) return console.error(error);
       svg.append("path")
           .datum(topojson.feature(uk, uk.objects.subunits))
           .attr("d", d3.geo.path().projection(d3.geo.mercator())); 
    });

We are going to go through this line by line.

`d3.json` should look familiar. It is not unlike jQuery's `$.getJSON`. It is an asynchronous call to a remote JSON file that, on return, executes a callback with two arguments. 

The callback starts with a line for error logging, which only executes if the `error` argument is defined. The second line then continues over three lines, which stripped down looks like this:

    svg.append(arg).datum(args).attr(args);

Let's pick these apart.

`svg` is defined higher up the document:

    var svg = d3.select("body").append("svg")
        .attr("width", width)     
        .attr("height", height);  // width and height are defined elsewhere

Although most of you have not been using jQuery this way, this is analogous to something like this:

    var svg = $("body").append("svg")
        .attr("width", width)     
        .attr("height", height);

This may be a bit more familiar:

    var svg = $("body").append('<svg width="' + width + '" height="' + height + '"></svg>');

Although, arguably, the first version is more readable.

The `svg` variable is a function that returns a new `svg` element inside the `body` element to which new HTML elements can be added. This variable can be re-used. 

Let's return to the original line and look at it piece by piece:

    svg.append("path")

This is taking the original `svg` element and appending a `path` element inside it. Expanded, it looks a bit like this:

    d3.select("body").append("svg").append("path")

Which produces:

    <body>
        <svg>
            <path></path>
        </svg>
    </body>

Onto the next line:

           .datum(topojson.feature(uk, uk.objects.subunits))

`topojson.feature` is the magic that turns a TopoJSON object into a GeoJSON object. Recall, [TopoJSON](https://github.com/mbostock/topojson/wiki) is a neat way of representing complex geometries such as occur in maps. These need to be converted back to GeoJSON for manipulation in an HTML document. The two arguments consist of the returned TopoJSON data `uk` and the bit of that data that contains the topological information `uk.objects.subunits`. You may want to inspect the source of the returned `uk.json` file, to make sure that it does in fact contain an `objects.subunits` object.

[`datum()`](https://github.com/mbostock/d3/wiki/Selections#datum) is a D3 method that returns some element of a GeoJSON object converted into a form that can be used in an HTML document.

Take care. A similar method is [`data()`](https://github.com/mbostock/d3/wiki/Selections#data), which returns an array of data. You need to be clear about whether the feature you have previously returned is a single object to be translated into a single path or an array of objects to be turned into several paths.

So, finally, we have:

    .attr("d", d3.geo.path().projection(d3.geo.mercator()));

The `attr()` method should be familiar. Here, we are adding a `d` attribute to the already-defined `path` element. The value of that attribute is the tricky bit. 

    d3.geo.path().projection(d3.geo.mercator())

The [`d3.geo.path()`](https://github.com/mbostock/d3/wiki/Geo-Paths) method returns a path generator suitable for adding to the `d` attribute of a `path` element. 

The `d3.geo.mercator()` method applies a [D3 projection](https://github.com/mbostock/d3/wiki/Geo-Projections).

The final bit of magic going on here (which is a kind of magic that you should now be getting familiar with) is that when you concatenate functions using the `.` notation, the output of one function becomes the input of the next function. So, in this case, the output of `datum()` is inserted as the single argument of `d3.geo.path()`, the output of which is then inserted as the single argument of d3.geo.mercator()`.

So, to return to the original snippet:

    d3.json("uk.json", function(error, uk) {
       if (error) return console.error(error);
       svg.append("path")
           .datum(topojson.feature(uk, uk.objects.subunits))
           .attr("d", d3.geo.path().projection(d3.geo.mercator())); 
    });

this can be read as:

> Go and get the a json file of map data and when it returns (assuming no errors), add a path inside the previously-created svg element, take the returned map data, convert it into a usable form, apply a suitable projection, and add it as a `d` attribute to the newly-created path element.

