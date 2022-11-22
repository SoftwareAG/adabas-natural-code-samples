The quote (double-quote) and apostrophe (single-quote) are not identical in their use, and the differences can be quite handy. 
See how to use them without the common mistake of coding hexadecimal literals.

Alphanumeric literals are delimited with apostrophes. To embed an apostrophe within a literal, we insert two apostrophes - in line with the 'matching pairs' rule.  
By default, Natural translates quotes to apostrophes, so it might be considered more legible to insert a quote.  

Look at **part 1** of the code example to see the two methods of writing the name O'Brien (two apostrophes vs quote).
```bash
1 Name with apostrophe: O'Brien  O'Brien
```

In **part 2** we want to surround part of the literal with quotes. Instead we get apostrophes which are a bit confusing.
```bash
2 Searching for 'O'Brien'
```

A common solution is to compress the hexadecimal representation of quote with the other parts of the string, as seen in **part 3**. 
The problem here is that this means the code cannot be run cross-platform - EBCDIC vs ASCII.  

In **part 4** we use the OPTIONS statement, a compiler directive, to change Natural's default action.
OPTIONS TQMARK=OFF

**Part 5** demonstrates how standard literals can be used instead of hexadecimal constants.
 
BONUS:
Natural knows to accept the contents of a literal as is, with no case translation. But there are situations where uppercase is necessary.  

For example, a subprogram name must be entered in upper case (on the mainframe).
```bash
CALLNAT 'SUBPNAME'
```

To ensure that literals are in uppercase, you delimit them with quotes. Natural still recognizes the literal string, but does not apply the "do not translate" rule as with the use of apostrophes.  
This feature can be used as documentation.  That is, it tells the maintenance programmer "This literal is intended to be uppercase only."
```bash
CALLNAT "SUBPNAME"
IF  #A = "Y"  OR = 'y' ...
EXAMINE #TEXT FOR "ABC" ...
```
