## Considering INIT (and Data Formats)

One way to follow the well-known Natural coding rule "the fewer the statements, the better", is to use the INIT clause when defining variables rather than setting the initial value with ASSIGN or MOVE.

Prior to the execution of a programming object, Natural executes a RESET INITIAL of all the LOCAL variables defined within the object.  By using INIT to set a starting value, we avoid the execution (interpretation) of an explicit assignment statement.  The "intialization section" of a programming object should be limited to assignment of PDA elements, dynamic variables, and X-arrays, for which INIT is not possible.

INIT can be used with all data types, as demonstrated in the code sample.  Both literals and System Variables may be specified as the value.
