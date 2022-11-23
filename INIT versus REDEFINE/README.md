INIT allows us to eliminate statements from the "initialization" section of our programs, that is, statements immediately prior to the mainline. 
Too bad that we can't use INIT for redefinitions.
                                                      
**PROGRAM 1**

Often we define a large alpha variable, then REDEFINE it to specify its components (structure).  
The INIT keyword is not allowed on the redefinitions, so we code explicit ASSIGN statements.  
In our example, we use the redefinition of the starting value of a superdescriptor from the Employees file.

**PROGRAM 2**

For small structures, as in the example above, we have the option to initialize the "large alpha", but for complex structures this would be unwieldy and difficult to read and maintain.

**PROGRAM 3**

A simple solution is to flip the redefinitions.  
We start with a structure and redefine it to be the "large alpha."
