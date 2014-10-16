# D3: Queue.js

D3 often requires large geodata files that can be a burden to load for your browser. Some action has been taken to reduce file sizes (the creation of topojson) but sometimes you just have a dataset that is as small as it can get, yet still pretty large. If you’ve run into this problem, you may have noticed your D3 code running before your file has actually loaded, which pooches the whole thing. 
### Queue is a lightweight asynchronous helper library. 

It is especially useful to use when you are loading multiple datasets into your code. In the following example, we’ll load two files; 

•	topojson of US States &
•	geojson of US Populated cities

You would need to load queue library after D3 library:   

       <script src="http://d3js.org/queue.v1.min.js"></script>

Queue parts:

•	queue() – initializes Queue.js and your loading queue
•	defer() – used for each file to allow them to load separately
•	await() – the final piece, which typically runs a function once the data are loaded

### The Queue

     queue()
       .defer(d3.json, 'states.json') // topojson polygons
       .defer(d3.json, 'cities.json') // geojson points
       .await(makeMyMap); // function that uses files

### Call Function

       function makeMyMap(error, states, cities) {
          svg.append('path')
           .datum(topojson.feature(states, states.objects.usStates))
           .attr('d', path)
           .attr('class', 'states');
         svg.selectAll('.cities')
          .data(cities.features)
          .enter()
          .append('path')
          .attr('d', path.pointRadius(5))
          .attr('class', 'cities');
        }

This loads multiple files before the code is run to preserve any actions or transitions your data may take before they load.




