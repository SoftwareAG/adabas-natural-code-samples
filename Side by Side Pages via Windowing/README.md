## Side by Side Pages via Windowing

In [Side by Side Columns via Windowing](https://github.com/SoftwareAG/adabas-natural-code-samples/tree/main/Side%20by%20Side%20Columns%20via%20Windowing) we looked at how to use windowing to display non contiguous columns side by side.

In this sample we will display different pages of the same program (or different programs) side by side in windows.

Suppose I have a program that produces separate pages of output for different departments of a company. 
Someone wishes to compare the shipping department with the marketing department. 
If the report were printed, someone would thumb through the pages of output until the two departments' pages were located, then hold them up side by side. 
This program lets you do this on the screen. The program is also useful for comparing an old and a new version of a program. 
Thus, developers as well as end-users will find use for the program.
 
The interesting thing is how simple this 'system' is.
 
There are two programs which I have imaginatively named LEFT and RIGHT. The two programs are functionally identical. 
The differences? LEFT has a SET CONTROL statement which creates a window on the left half of our screen. 
The matching SET CONTROL statement in the program called RIGHT creates a window on the right side of our screen.
 
There is a driver program which starts the system. Functionally, this is also quite simple. 
It RESETs several Global Variables, places any information the end-user might need on the screen, and finally, transfers control to whichever program (LEFT or RIGHT) the end-user wishes to see initiated first.
 
There are many ways to customize this program. 
It is quite trivial to change the screen split. 
As presented, RIGHT and LEFT are each allocated half the screen. 
You can change this in less than a minute.
 
There is no requirement that the two programs (named LEFT and RIGHT) be the same program. 
They can be totally different programs, or different versions of the same program, or, as in our example, the same program.
 
It is quite trivial to customize the heading on the top of every page by using a WRITE TITLE override. 
One use of this facility would be to put the page number in two places on the top of every page. 
Thus, you could see the page number whether looking at the left or right side of a pop-up window.
 
The driver program, LEFTRITE, has an INPUT statement. 
Any text that is placed there, below where the pop-up windows will be, is visible on the screen. 
I used this space for information regarding the PF key assignments to scroll left and right within a pop-up window.

Please see the [Example Output](example.txt) and the [Program Code](program.txt).
