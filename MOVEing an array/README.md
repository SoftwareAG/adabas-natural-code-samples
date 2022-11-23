## MOVEing an array

This programs compares CPU and elapsed times for three techniques for MOVE'ing one array to another (copying an array).

The three techniques are:
1. NATBOL (a FOR loop through the array)  
2. An array level MOVE   
3. A string MOVE (a REDEFINE of the array)

There are two outputs, PC and Mainframe.

For both PC and Mainframe, the performance of the NATBOL code is terrible. It should not be used for this functionality.

On the PC and the Mainframe, the efficiency of the string MOVE is apparent. 
On the PC, after subtracting out the common FOR loop, the ration is about seventy to one in favor of the string MOVE when compared with the array MOVE.
On the mainframe, after subtracting the FOR loop, the ratio is about two to one in favor of the string MOVE.

YET, in code I have seen around the world, the NATBOL code is most prevalent, followed by the array MOVE, followed by the string MOVE.