# CSS Resets

You may have noticed through inspecting elements on a page that there is a user-agent stylesheet applied to the page’s elements. The user-agent stylesheet (which is dictated by the browser you’re using) applies a lot of ‘off-the-rack’ css properties to elements effecting, in particular, things like margin and padding. 

If you’re looking to make something quickly, and across platforms, it can often be frustrating to see that elements sit in a way that you didn’t anticipate or in a way you don’t want on the page. In such circumstances it is tempting to use a css reset to simply cancel all of that stuff out.

At its most basic the Universal Selector CSS Reset looks like this:

```
* {
	margin: 0;
	padding: 0;
}
```

_but an extended version might look like this:_

```
* {
	margin: 0;
	padding: 0;
	border: 0;
	outline: 0;
	font-size: 100%;
	line-height: 1.5em;
	text-decoration: none;
	vertical-align: baseline;
}
```

_This will effect all elements in the document and remove any spacing around and between them._

###When is it a good idea to include a reset like this?###
*for high speed website prototype development it is suitable, but probably best not to use on complex or big websites (or for the final product)!
_In this context it can be helpful for understanding the basic flow of the elements on a page in their unaltered state._

###When is it not a good idea to include a reset?###
**Under any other circumstances.**
*Every element in the document is effected by the reset and so must have their style properties addressed individually.
*Since this is a universal declaration which effects every element in a document, and css alterations that have an affect on layount, paint, and composite increase load time, there is an argument that such a universal reset is an unnecessary strain on load times. [See the blog behind Css Triggers](http://csstriggers.com/)
A reset like this will also have a particularly noticeable effect on `<input>` elements. [See here](http://jsbin.com/vokol/latest)

*Harry, FAC3*