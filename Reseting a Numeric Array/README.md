## Reseting a Numeric Array

This program compares several techniques for RESET'ing a numeric array.
There are several interesting results from the timing comparison.

This program is quite similar to the comparison for different techniques to RESET an Alpha array.

I was looking for a *numeric* equivalent to the RESET of an long alpha variable which was a REDEFINE of the Alpha array.
I came up with the idea of using a MOVE ALL statement. Then I realized I could change the MOVE ALL to a MOVE of an Alpha variable whose value was simply a string of zeroes. 
Much to my surprise, the MOVE ALL outperformed the MOVE ALL Variant (which is just a MOVE).

**Also of note**
 
On the mainframe, the Natural compiler *recognizes* statements where code like #ARRAY (\*) can be treated as if they were simply a string. 
For example, take a look at the ARRAY time for the mainframe (which reflects a RESET #ARRAY (\*)). 
This is the fastest approach on the mainframe. 

Yet on the PC, where the compiler seems not to be taking this into account, the ARRAY time is in third place.
Also, take a look at the MOVE ZERO times on the PC (exceedingly slow compared to the other techniques) and on the Mainframe (still in last place but not nearly as slow when compared with the other techniques).


### Conclusions:

On the Mainframe, use the RESET #ARRAY (\*). It is not only easier to read, it is faster than all other approaches.
On the PC, use either of the MOVE ALL approaches. 
BUT, use comments so a reader understands the code. 
Also, make sure you have the proper Hex equivalent of zero for your platform, AND, note that this code will not be portable across platforms.
