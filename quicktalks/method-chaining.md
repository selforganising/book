#Method Chaining

##What is it?

Mocha example

describe('When a user goes to the home page', function() {

    it("should return sucessful status code", function(done) {
        request.get('/')
            .expect(200, done);
    });
}) 

A way of simplifying your code when calling multiple methods on an object.

##Why do people use it?

Save time/space!
For example, this is something we might do in Jquery when setting lots of properties for an object.

    var $div = $('#my-div');         
    $div.css('background', 'blue');  
    $div.height(100);                
    $div.fadeIn(200);

With method chaining can become:

    $('#my-div').css('background', 'blue').height(100).fadeIn(200);

Or (as Air BnB prefer):

    $('#my-div')
      .css('background', 'blue')
      .height(100)
      .fadeIn(200);

What a transformation!

Some developers don't like it, but you need to know for when you read other's code.

##But be careful!

You can't use these willy-nilly!

If your method doesn't return the object, you can't use them.
What do I mean by that?

###Creating kittens

Imagine you've made a kitten object and you've created multiple methods like this:

    // define the class
    var Kitten = function() {
      this.name = 'Garfield';
      this.color = 'brown';
      this.gender = 'male';
    };
    Kitten.prototype.setName = function(name) {
      this.name = name;
    };
    Kitten.prototype.setColor = function(color) {
      this.color = color;
    };
    Kitten.prototype.setGender = function(gender) {
      this.gender = gender;
    };

That's going to let you do something pretty cool - create new kittens!

    var bob = new Kitten();
    bob.setName('Bob');
    bob.setColor('black');
    bob.setGender('male');

###There must be a better way

But that looks like a lot of effort doesn't it? Can't we use method chaining?

Well actually we've got a problem if we try something like this:

    var bob = new Kitten();
    bob.setName('Bob').setColor('black');

We're going to get an error:

    // ERROR:
    // > Uncaught TypeError: Cannot call method 'setColor' of undefined

###Why are we getting an error?
Well if you stretch it out, it's actually going to look like this:

    var bob = new Kitten();
    var tmp = bob.setName('Bob');
    tmp.setColor('black');

bob.setName isn't something you can apply a method to. It's not an object itself.

We can get around this problem when we create our methods. Let's go back up to our methods and change them so they will work in a chain.

###Returning the object

    // define the class
    var Kitten = function() {
      this.name = 'Garfield';
      this.color = 'brown';
      this.gender = 'male';
    };
    Kitten.prototype.setName = function(name) {
      this.name = name;
      return this;
    };
    Kitten.prototype.setColor = function(color) {
      this.color = color;
      return this;
    };
    Kitten.prototype.setGender = function(gender) {
      this.gender = gender;
      return this;
    };

Now this makes sense:

    var bob = new Kitten();
    var tmp = bob.setName('Bob');
    tmp.setColor('black');

Great! What a time saver!

###Further reading:
This is mainly a summarised version of this helpful page:
http://schier.co/post/method-chaining-in-javascript

##Bonus: Air BnB

Use indentation when making "long" method chains. (Maybe shorter ones are at your discretion?)

    // bad
    $('#items').find('.selected').highlight().end().find('.open').updateCount();
    // good
    $('#items')
      .find('.selected')
        .highlight()
        .end()
      .find('.open')
        .updateCount();
