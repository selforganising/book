#Using GeoJSON and TopoJSON
##What is topojson.feature(world, world.objects["world.geo"]).features actually doing?*

##What is GeoJSON vs TopoJSON?

TopoJSON is a lightweight version. The big difference is the arcs.
Arcs are a path made of coordinates. When you make a TopoJSON object you reference the arcs rather than the coordiantes themselves.Why?
This way you don't double up on lines. E.g. map of the world! We don't need a line for Scottish/English border and the English/Scottish border - one will do!

e.g. page 19,20,21: http://www.somebits.com/~nelson/SotM-2013-TopoJSON.pdf

##So can I just forget about GeoJSON?

Not so fast kiddo! GeoJSON still has an important role to play. When you start drawing the map, working directly with TopoJSON won't work. We can't use the arcs to draw. You can't directly access the coordinates.

GeoJSON on the other hand can be used with this great function:

d3.geo.path()
This goes into a feature of your GeoJSON and pulls out your coordinates without any further instruction! It's great! 

If only there was a way to store your files in TopoJSON, so as to not double up on borders, but have the ease of drawing paths with GeoJSON files! Well now there is!

topojson.feature(topoJSON-file, array-you-want-to-make-into-geoJSON)

OK, so that explains this:

 topojson.feature(world, world.objects["world.geo"])

##But what is .features doing?

Well, let's have a look at our new GeoJSON format...

features is in all GeoJSON files...


*this question is based around the code used for this: http://foundersandcoders.org/resources/d3/minimal.html
