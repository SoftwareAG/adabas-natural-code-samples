## Dates, IS and VAL

Inputting dates can be problematic, especially in international applications.  
Using IS and VAL may simplify things.

Natural allows the entry of date values into D-format fields, but this option is rarely used in our applications because bad data causes a Natural error to be displayed and we prefer to maintain control and display our own messages.  
So we enter date values into alpha fields and use MASK to verify format and content.  
Then MOVE EDITED is used to convert the alpha value to D format.

Different users may prefer different date formats, so 

**Program 1** 

uses a set of MASKs to determine which one is being used. Delimiters / and - are needed to differentiate between mmdd and ddmm sequences, because if the day is prior to the 13th, there is no way to distinguish between them.  
For example, is 04/01 April 1 or January 4?

But what if all users prefer slashes?
Natural supports US, German, European, and International formats as mm/dd/yyyy, dd.mm.yyyy, dd/mm/yyyy, and yyyy-mm-dd, respectively.  
For each user the format of choice is specified in the DTFORM parameter.  
If we allow the user to enter dates in his preferred format, then we needn't worry about the mmdd vs ddmm issue.

**Program 2** 

demonstrates how date format is enforced using Natural's IS and VAL functions. 
The program is compiled once. At execution time, the IS option applies the date format as specified by the DTFORM parameter.
