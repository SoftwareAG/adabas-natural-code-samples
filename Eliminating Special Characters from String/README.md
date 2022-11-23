## Eliminating Special Characters from String

This program shows several ways to eliminate Special Characters from a string.
The performance comparison indicates that what might be a counter intuitive fastest alternative is indeed the best performing of the three alternatives shown.

This program contrasts three ways to accomplish a seemingly simple task. 
There is an alpha string, formatted A24. There are some special characters (three in our example), that must be removed from the string.
 
There was a posting by someone who was looking for a faster way to accomplish this than the existing code. The existing code was a disaster, a wonderful example of Natbol code. 
I won't ruin the story for you, just take a look at the code whose output is labeled 'Loooong Time'.
 
The first thing that came to mind was to use SEPARATE with the three special characters as delimiters. This was indeed far faster than the Natbol code.
However, Natural has an even faster alternative. 
Yes, I know this may seem counter intuitive, but three EXAMINEs with DELETE options turns out to be far faster than the SEPARATE.
