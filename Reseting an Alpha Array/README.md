This program contrasts three ways to set an Alpha Array to null values.
The timing comparison is quite interesting.
 
As with other related comparisons; the string approach is more efficient on both the PC and the mainframe.

On the mainframe, the RESET #ARRAY(\*) is almost as efficient as the string approach, but on the PC, after subtracting out the FOR loop, the string time is just one third the array time.

The MOVE ' ' approach is about three times as long as the string approach on the mainframe.
HOWEVER, on the PC, the MOVE ' ' approach is over 100 times as slow as the string approach.

Once again, the string approach, based on efficiency, is better than any approaches which utilize the array syntax.
