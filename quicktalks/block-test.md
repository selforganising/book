#Blocks

### What is a block?

* In computer programming, a block is a section of code which is grouped together. 
* Blocks consist of one or more declarations and statements. 
* A programming language that permits the creation of blocks, including blocks nested within other blocks, is called a block-structured programming language. 
* Blocks are fundamental to structured programming, where control structures are formed from blocks.

### Why is it important to use blocks?

* Blocks allow us to create a good practice structure. 
* The function of blocks in programming is to enable groups of statements to be treated as if they were one statement. 
* Blocks narrow the lexical scope of variables, procedures and functions declared in a block so that they do not conflict with variables having the same name used elsewhere in a program for different purposes. 
* In a block-structured programming language, the names of variables and other objects such as procedures which are declared in outer blocks are visible inside other inner blocks, unless they are shadowed by an object of the same name.

* Use braces with all multi-line blocks.

BAD
        if (test)
          return false;
  
GOOD
        if (test) return false;

GOOD
        if (test) {
        return false;
        }

BAD
        function() { return false; }

GOOD
        function() {
        return false;
        }


# ESSENTIALLY
     
The block structure makes it easier to see how the code could be refactored for clarity, and also makes it easier to do, because the structure of the inner conditional can easily be moved out of the outer conditional altogether and the effects of doing so are easily predicted.
   
