# Regular Expressions


### What the feature is

Regular expressions - or regexs for short - is a technique used for matching strings and are a way of searching text for patterns. It can be used for evaluating whether a string starts with a capital A or whether an email address has the right format.

This you can also do with normal string functions but regexs offers greater flexibility. Regexs is a very powerful tool for any programmer and it is well worth taking the time to learn it. Once learned you will wonder how you could ever live without it and will probably never go back to using string methods.

In Regexes you can include words, numbers or patterns.


### How you would use it

Regexes are usually defined between forward slashes:

/re/


In the early computer days, UNIX implemented regular expressions inside an UNIX text editor, ed. It looked like this

g/re/p

where the g was telling you to do a global search and the p was to print out the results to the screen.

(Remember grep? Grep is used to search for texts from a file or another command's output and prints it afterwards. Maybe another Quicktalk? :) )


### Why you would use it

Once you get a hang of it, you can use it in so many cases:

- Test if a number has correct the correct number of digits
- Tests if an email address is in a valid format
- Search a document for either "color" or "colour"
- Find duplicate words in a text
- Get rid of whitespace


### When you might not use it

You might not use it if you are looking for a specific expression even though you can use regular expressions for it as well. 


### How to use it

There are plenty of commands to use regular expressions. Dowload the Cheatsheet below to get an overview.

You can use regular expressions in Sublime Text as well. 


### Examples

###### Get rid of white space
1. Do a Regex search and replace
2. Search for /^[ \t]+/
3. Replace with nothing to delete leading whitespace

###### Trim trailing whitespace
1. Do a Regex search and replace
2. Search for /^[ \t]+$/
3. Replace with nothing to delete leading whitespace


### Be Careful
Catastrophic Backtracking. If your regular expression seems to take forever, or simply crashes your application, it has likely contracted a case of catastrophic backtracking. The solution is usually to be more specific about what you want to match, so the number of matches the engine has to try doesn't rise exponentially.

Making Everything Optional. If all the parts in your regex are optional, it will match a zero-length string anywhere. Your regex will need to express the facts that different parts are optional depending on which parts are present.


#### Resources

1. [8 regexes you should know](http://code.tutsplus.com/tutorials/8-regular-expressions-you-should-know--net-6149)

2. [Some Tools and further resources for RegExes](http://www.hongkiat.com/blog/regular-expression-tools-resources/)

3. [Downlaod the RegExp Cheat Sheet (just click on "Buy Now" and enter $0  and your email adress to get it for free)](https://www.addedbytes.com/cheat-sheets/regular-expressions-cheat-sheet/)

4. [Some examples and explanations on Regexes](http://www.jslab.dk/articles/introduction.to.regular.expressions.using.javascript.part1)
