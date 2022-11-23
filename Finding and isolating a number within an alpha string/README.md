This sample demonstrates  a fast way to find a string of three integers within an Alpha string that did not contain any other integers.

**The first program**
shows five techniques; the output shows that all five produce the same correct answer.
The program employs a MASK to locate the first Integer, then three MOVEs to isolate the three digit number. 
There is a similar sample which uses a substring MOVE rather than the three MOVEs. The performance of both these approaches was similar.

**The second program**
uses three techniques with SEPARATE, which has timing comparisons, the SEPARATE techniques are about three times as fast as the MASK techniques on the mainframe. 

On the PC, they are 4-5 times as efficient.
