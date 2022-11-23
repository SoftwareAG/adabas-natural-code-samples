## Side by Side Columns via Windowing

This program shows how to use windowing to display non contiguous columns side by side.

Suppose I have a printout of a spreadsheet. 
The rows represent different products. The columns represent different month's orders. 
I want to compare January's orders against September's orders. 
This is not difficult; I simply fold the paper so that the two columns are side by side. 
If I want to compare different months, I next fold the paper again, etc.
 
Okay, now I have the same spreadsheet on the screen. 
Same requirement; compare two different months' orders. 
Natural's windowing commands make this a fairly simple task. 
The program posted here is designed to create one or two pop-up windows. You can place the same, or different months in each pop-up window. 
Thus, if I want to compare January versus September, I would move the cursor a bit to the right of January. I would hit the proper PF key (PF2) and I would see a pop-up window with January in it. 
I could then use PF8 to scroll within the window to September. 
Alternatively, I could have used PF4 to change the screen from Jan-July to Aug-Dec. Then I could have moved the cursor to one side of September and hit PF2 to create a pop-up window with January.
 
There are many ways to customize this program. 
For example, the %WA command permits the saving of a screen image before the screen is overlaid by a window. 
Then, if the window is moved, the old window is removed. 
Translation. 
In our program, the second PF2 would remove a window from the first PF2. 
The program can be adapted to horizontal rather than vertical windows. 
A bit of additional programming can accommodate variable width vertical columns (realize that same width probably dominates variable width in terms of frequency of use).
 
There will be another program posted here that uses windowing to display two screens side by side. 
Suppose I have a program that produces separate pages of output for different departments of a company. 
Someone wishes to compare the shipping department with the marketing department. 
If the report were printed, someone would thumb through the pages of output until the two departments' pages were located, then hold them up side by side. 
This program lets you do this on the screen. The program is also useful for comparing an old and a new version of a program. 
Thus, developers as well as end-users will find use for the program.

Please see the [Example Output](example.txt) and the [Program Code](program.txt).
