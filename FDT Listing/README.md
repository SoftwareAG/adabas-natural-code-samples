## FDT Listing

Not everyone has access to DBA Workbench, so here's a Natural program to list an FDT. 
* USR1043 executes the LF Adabas command. 
* USR1028 translates a byte into a bit pattern.

This program was written and tested in Nat6.2 and should work in Nat4.2. For Nat3.1 and Nat4.1, remove the SET GLOBALS statement.

Rename the attached source module with an NSP extension, drag-n-drop it onto a Natural library, and RUN.