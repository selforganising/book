# Comments

Commenting involves placing Human Readable Descriptions inside of computer programs detailing what the Code is doing. Proper use of commenting can make code maintenance much easier, as well as helping make finding bugs faster. Further, commenting is very important when writing functions that other people will use. Remember, well documented code is as important as correctly working code.

http://www.cs.utah.edu/~germain/PPS/Topics/commenting.html

### Single line Comments

* for single like comments, place on a new line above the subject of the comment.

BAD

		// bad
		var active = true;  // is current tab

GOOD

		// good
		// is current tab
		var active = true;

BAD

		// bad
		function getType() {
  			console.log('fetching type...');
  		// set the default type to 'no type'
  		var type = this._type || 'no type';

 			return type;
		}
GOOD

		// good
		function getType() {
		  console.log('fetching type...');

		// set the default type to 'no type'
		var type = this._type || 'no type';

		  return type;
		}


### Multiline Comments

* Inside multiline comments include a description specifying details like types and values of parameters and return values 

BAD

		// bad
		// make() returns a new element
		// based on the passed in tag name
		//
		// @param <String> tag
		// @return <Element> element

GOOD

		// good
		/**
 		* make() returns a new element
 		* based on the passed in tag name
 		*
 		* @param <String> tag
 		* @return <Element> element
 		*/

### Prefixing

* Prefixing your comments with `FIXME` or `TODO` helps other developers quickly understand if you're pointing out a problem that needs to be revisited, or if you're suggesting a solution to the problem that needs to be implemented. These are different than regular comments because they are actionable. The actions are `FIXME -- need to figure this out` or `TODO -- need to implement`.

* Use `// FIXME:` to annotate problems

		function Calculator() {

		  // FIXME: shouldn't use a global here
		  total = 0;

		  return this;
		}

* Use `// TODO:` to annotate solutions to problems

		function Calculator() {

		  // TODO: total should be configurable by an options param
		  this.total = 0;

		  return this;
		}


### When Not to Use Comments

* Comments should be used to describe what a program is doing, but not restate something that is obvious. 
* By using appropriate and informative variable names there isn't a need for a comment in that instance.

*Natalia, FAC3*