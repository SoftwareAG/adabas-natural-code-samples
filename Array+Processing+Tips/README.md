It may not be necessary to code an explicit loop, such as FOR or REPEAT, to process an array.

Here are simple methods to

* shift elements to the left (pop-up)
* shift elements to the right (push down)
* sum a set of elements

**Program 1 - Shift left/up**  
Shifting up requires a single ASSIGN.

**Program 2 - Shift right/down**  
Shifting down requires a temporary duplicate array and two ASSIGNs.

**Program 3 - Sum**  
Invariably a FOR loop is used to sum the contents of an array, as in Program 3a, but a single computation can determine the sum of all (or a range of) array elements, as in Program 3b.  

**Program 4 - Display**  
DISPLAY places the elements of an array on individual lines.  No explicit loop is needed.  See Program 4a.

A loop is not necessary to exclude empty array elements from the report.  The DISPLAY statement can be told to ignore them, as in Program 4b.  This is especially helpful when an array is defined with many occurrences, but few are populated, because we get a more condensed report.
