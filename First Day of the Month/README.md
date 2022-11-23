## First Day of the Month

This code shows two ways to derive the first day of the month for both alpha and date formatted dates.

The code in this program is heavily commented to describe the procedures.
Subsequent posts will build on this code to derive the last day of the month preceding a given date and to derive the last business day of the month preceding a given date.

There are two copycode members used; and they are shown below:
 
**AASETC**

This is structured mode. In Report Mode the END-ENDPAGE would not appear.

```bash
AT END OF PAGE
   SET CONTROL 'C'
END-ENDPAGE
```
 
**AATITLER**

```bash
WRITE TITLE LEFT   5T 'PAGE #' *PAGE-NUMBER (NL=2)
                  35T 'DATE:   ' *DATX /
                   5T 'PROGRAM:' *PROGRAM
                  35T 'LIBRARY:' *LIBRARY-ID /
```
