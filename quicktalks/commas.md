#Commas

###When do we use commas and what is their purpose?

  - Key use: as separator 
  - As operator 

The simplest and most common use of commas is simply as a separator in an expression. 

E.g. in object literals:
var obj={a:0,b:1,c:function(){}};

In arrays:
var arr=[1,2,3,4];
the commas are just separators.

In the var declaration. For example in:
var a=1,
    b=2,
    c=3;

###Best practice rules:

1) Always use semicolons to terminate statements - a comma will never do the same job<br>
2) Don't use leading commas<br>
3) Don't use a comma after the last item of an array

###Leading Commas

// bad
var once
  , upon
  , aTime;

// good
var once,
    upon,
    aTime;

// bad
var hero = {
    firstName: 'Bob'
  , lastName: 'Parr'
  , heroName: 'Mr. Incredible'
  , superPower: 'strength'
};

// good
var hero = {
  firstName: 'Bob',
  lastName: 'Parr',
  heroName: 'Mr. Incredible',
  superPower: 'strength'
};

### The Additional Trailing Comma

  // bad
  var hero = {
    firstName: 'Kevin',
    lastName: 'Flynn',
  };

  var heroes = [
    'Batman',
    'Superman',
  ];

  // good
  var hero = {
    firstName: 'Kevin',
    lastName: 'Flynn'
  };

  var heroes = [
    'Batman',
    'Superman'
  ];
  
This additional comma can cause problems with certain browers, notably IE6/7 and IE9 if it's in quirksmode. It could add additional length to an array in certain browsers.

###Comma as an operator...?


The comma can also be used as an 'operator' - this is a more complicated use of commas and can often lead to programming errors when used incorrectly.

The comma operator is an operator that can be used inside an expression. It is used to separate out multiple different expressions and has the meaning "evaluate all of the following expressions, then produce the value of the final expression." For example:

a = 1, b = 2, c = 3
means "evaluate a = 1, then b = 2, then c = 3, then evaluate to the value of the expression c = 3.

*When should you use the comma as an operator?

To be safe, never.

There are places, espcially in libraries, where you will find the comma operator in use, but in most cases there are much better and clearer ways of expressing the same idea. 

The most commonly encountered use of the comma operator is to make more complex for loops. 

E.g.

for(var i=0,j=10;i<=j;i++,j--){ 
 console.log(i*j); 
}

The first expression just uses the var statement to create two local variables, i and j, and sets them to zero and ten respectively. The second expression is a simple test for i being less than or equal to j, and doesn't use the comma operator. 
The final expression is the only use of the comma operator and it adds one to i and subtracts one from j each time through the loop. So the values of i and j we create are:
0 10
1 9
2 8
3 7
4 6
5 5
and then the loop ends.

An alternative, simpler version is:
for(var i=0,j=10;i<=j;i++){
 console.log(i*j);
 j--;
}

##BASICALLY, never use the comma as an operator. You might see it being done, but it is not good practice.
--------
*Natalie, FAC3*
