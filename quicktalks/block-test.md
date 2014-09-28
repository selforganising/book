#Blocks

### What is a block?

* In computer programming, a block is a section of code which is grouped together. 
* Blocks consist of one or more declarations and statements. 
* Use braces with all multi-line blocks.

BAD
        function() { return false; }


GOOD
        function() {
        return false;
        }

### Why is it important to use blocks?

* Blocks allow us to create a good practice structure. 
* The function of blocks in programming is to enable groups of statements to be treated as if they were one statement. 

BAD
        if (test)
          return false;
  
GOOD
        if (test) return false;

GOOD
        if (test) {
        return false;
        }

# ESSENTIALLY
     
* Block structure makes it easier to see how the code could be refactored for anyone using it. 