This assemblage of programs addresses an interesting problem. How best to locate and change the last occurrence of a character in an alpha variable.

On a PC, there is a powerful option for the EXAMINE statement which "examines" the target variable right to left rather than left to right. 
This option does not exist on the mainframe.
There is a little known option, PM=I, which can reverse the order of characters in a variable. This is the fastest way to perform this function on a mainframe.

> Summary
On a PC, use EXAMINE BACKWARD, on a mainframe, use PM=I.
