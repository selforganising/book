# Variables

### What are they ?

* A script will have to temporarily store the bits of info it needs to do it's job. This data can be stored in VARIABLES. The data stored within a variable can change (or vary) !!

* They can hold strings, numbers, booleans, arrays and objects.

* Always use var to declare variables. Not doing so will result in global variables. We want to avoid polluting the global namespace.

BAD

    // bad
    superPower = new SuperPower();

GOOD

    // good
    var superPower = new SuperPower();
    
    
### Rules for naming variables.

1. The name must begin with a letter, dollar sign or an underscore. NOT A NUMBER

2. The name can contain letters, numbers, dollar signs or underscores. NOT DASHES (-) OR PERIODS (.)

3. You cannot use KEYWORDS or RESERVED words. (http://www.w3schools.com/js/js_reserved.asp)

4. Variables are case sensitive. It is bad practice to have two variables that have the same name using different cases.

5. The name should describe the data stored in the variable.

6. camelCase. DO IT

### Using one 'var' declaration for multiple variables.

* In general, you should declare each variable on its own line with an explanatory comment regarding its role. GOOD PRACTICE

* Use one var declaration for multiple variables and declare each variable on a newline. Declaring multiple variables in a single declaration could cause confusion about the types of variables and their initial values.

BAD

    // bad
    var items = getItems();
    var goSportsTeam = true;
    var dragonball = 'z';

GOOD?

    // good
    var items = getItems(),
        goSportsTeam = true,
        dragonball = 'z';
        
        
*Max, FAC3*