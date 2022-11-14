## Determine whether two files are identical - across databases and platforms.

This program determines whether the contents of two Adabas files are identical.  The files may reside in the same database or separate databases.  The databases may be on different hardware platforms (ie mainframe vs Windows vs Unix/Linux).

In-stream comments are provided for customization.

Despite the use of user exit USR4011N to compute the actual checksum values, this program can be quite CPU-intensive.  When comparing mainframe vs Windows files, I run the program on the Windows platform utilizing the Net-Work product to communicate with mainframe Adabas.  Use of desktop CPU units is more palatable than using mainframe CPU.
