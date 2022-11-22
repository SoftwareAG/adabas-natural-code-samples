When a literal string does not fit into a source line, a hypen is used to continue it on the next line.

Here is another use: fewer lines of code.

Four sample programs are provided.

**Program 1 demonstrates the hyphen's typical use in dealing with long character strings.**

**Program 2 is a standard reporting program.  **
We wish to display all contracts of type B (first superdescriptor component) in ID sequence (second SD component).

The results indicate that no records of type B exist. The first record read is of type M.

Program 2 Results:

End: M           1

But we happen to know that there are over 200 such records on file.  We realize that the second component of the SD is in packed-decimal format, so the first (and possibly several) bytes contains H'00'.  Our starting value contains a space in the first byte of the ID and this positions us at the next Type value in the file - M.

**Program 3 specifies low-values for the starting value of ID and all 9s for the ending value, so we report 202 IDs.**

Program 3 Results:

Page    11
 
CONTRACT-TYPE CONTRACT-ID
------------- -----------
 
B                2190
B                2191
B                2192
B                2193
B                2194
B                2195
B                2196
B                2197
B                2198
B                2199
B                2202
B                2205
 
End: B         202


And finally to the point of this posting.

**In Program 4 the start and end structures are removed. **
Start and end values are specified as literal strings, instead.  Fewer lines to code means fewer lines to debug/correct.  
Results are identical to those of Program 3.  The trick is knowing that Natural lets us concatenate alpha and hexadecimal strings.
READ TUR BY CONTRACT-TYPE-SP FROM "B" - H'000000000000'

This method also works with other field formats, such as date (their packed representation, actually), and integer.
