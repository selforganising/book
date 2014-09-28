#Actually using Sass
---
##Requires a plan
The best way to approach styling a document, not just with Sass, but especially with Sass, is to have a good plan of what you want things to look like before you start.

*To really get to grips with the details of using Sass - always refer to the [documentation](http://sass-lang.com/documentation/file.SASS_REFERENCE.html). From there you can just cmd + f what you're looking for.

###Some interesting features include
*Nesting - to logically represent the flow of the markup and allow others to join in to the styling process more easily
*Variables
*Mixins
*Doing maths - e.g. `.outterBox { .innerBox { width: $width; height: $width / 2; } }`

---
##Variables
If you're going to be using the same colour, or font, or border shape etc in a lot of different places, it's a good indicator that you should declare that property as a variable so that it can be used more easily in multiple places. 

##Mixins
The golden rule with mixins is: if you know that you'll be using a pattern of styles, or you find yourself coding in a similar pattern 2 of 3 times, you could reduce your workload with a mixin. 


