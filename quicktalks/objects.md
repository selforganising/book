#Javascript – Objects

##What is the feature?

Objects are just data, with added properties and methods. Object is the main data type in JavaScript. "Everything" in JavaScript is an Object.

Compare it with a cup, for example. A cup is an object, with properties.

A cup has a color, a design, weight, a material it is made of, etc. The same way, JavaScript objects can have properties, which define their characteristics.


##How would you use it?

Use the literal syntax for object creation

        // bad
        var item = new Object();
        // good
        var item = {};

Don't use reserved words as keys. It won't work in IE8. More info

        // bad
        var superman = {
        default: { clark: 'kent' },
        private: true
        };

        // good
        var superman = {
        defaults: { clark: 'kent' },
        hidden: true
        };

Use readable synonyms in place of reserved words.

        // bad
        var superman = {
        class: 'alien'
        };

        // bad
        var superman = {
        klass: 'alien'
        };

        // good
        var superman = {
        type: 'alien'
        };

##Why would you use it?

Objects are useful because

1.	They are stateful.

2.	They can store relations between strings and ata.

3.	It can be easier to decompose a problem by breaking it up into objects that collect related operations and state.

Without objects, you are going to have loose functions all over the place. This very often will result in code that is very difficult to maintain. At a bare minimum objects give you the ability to lump functions together in order to simulate namespaces-- and that's at a bare minimum.

##When to not use it?

*Maryam, FAC3*