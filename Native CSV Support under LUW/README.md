Under LUW (Linux/Unix/Windows) Natural offers built-in CSV support.

On the mainframe it is not possible to create a true CSV file, but one may be simulated by creating a fixed-length record of fixed-length fields with alpha values delimited by double quotes.

**Program 1 demonstrates how overly complicated the mainframe logic is.**  
The report and file output (simulated CSV file) are listed after the program.

**Program 2 uses Natural's native CSV support to simplify CSV creation.**  
Using the \*TRIM function, variable-length fields and records are written, with the potential to substantially reduce the size of the output file.  
Compare the output file contents (true CSV file) to that of Program 1.

**Program 3 reads the CSV created by Program 2.**

**Program 4 employs a user exit (USR2011N)**
to override Natural's default delimiter (semi-colon) to a comma so that the file created by Program 1 may be read.
