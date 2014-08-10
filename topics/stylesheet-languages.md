# Stylesheet languages

##What are they?

Stylesheet languages define the look of a document. CSS is the language used in all browsers. Several other stylesheet languages have been developed that can be converted, using a *preprocessor*, into CSS.

##Why would you want to use anything other than CSS?

You might want to define global variables, for example to define a global colour scheme, or nest your style definitions, or apply styles conditionally. CSS does not allow you to do this. Stylesheet languages have more expressive power than plain CSS and allow you to program your styles more like a conventional programming language.

##What are the choices?

[Sass](http://sass-lang.com/). The original stylesheet language, originally written just in Ruby, but also now available using npm. It uses two syntaxes: the original terse style, using indentation and newlines in place of parentheses and semi-colons, and the newer SCSS style that looks like CSS.

[Less](http://lesscss.org/). Inspired by Sass and in turn influenced the SCSS variant of Sass. Originally written in Ruby, now maintained in JavaScript and installed using npm. It is simpler than Sass (lacking conditionals and loops, for example), which some see as an advantage.

[Stylus](http://learnboost.github.io/stylus/). As flexible as Sass and with a very forgiving syntax. Claimed by its author (the prodigious [TJ Holowaychuk](https://github.com/visionmedia))to be the most CSS-like stylesheet language.

##Which one to use?

If you are using a CSS framework, like Bootstrap or Foundation, you will want to use a stylesheet langage that supports them. Bootstrap is built using Less and has an official Sass port and unofficial Stylus port. Foundation is built using SCSS. There is an also unofficial Stylus port.

If you not very familiar with CSS, then you may want to stick to CSS-like syntax, to avoid confusion.

Sass, Less and Stylus are all good choices, but Less using SCSS will probably support the majority of use cases and is perhaps the safest first choice.


