You know that the hyphen can be used to continue a literal string onto another line.  
It also can be used to make array initializations more legible.

**Program 1**

defines two internal tables, each with two columns - a code and its descriptive text.  
In each table the values in the columns have a one-to-one relationship.  
Because the columns are defined as vectors, it can be difficult to see that relationship.  
In fact the color table contains an error. The codes for Gray and Green are reversed, but this is not easily seen.


**Program 2**

uses hyphens to create visual columns.  
Here the column relationships are obvious and mismatches are easily seen.  
Despite the restructuring, no logic changes are required.


**Program 3** 

demonstrates that you can create a table with more than two columns, but for legibility, you want all column values to fit on a single source line.  
It also shows that column values are not limited to alpha strings.