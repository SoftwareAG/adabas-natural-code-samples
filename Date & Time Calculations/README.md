# Date & Time Calculations

No need for packed-decimal arithmetic using cryptic values, such as 864000 for "10ths of a second in a day."

Natural's Date and Time variables make it easy to code and easy to read.

Introduction  
=========

A D-format variable (4-byte packed decimal, internally (P6)) contains a date value in the range 1582-01-01 through 2400-12-31\. A T-format variable (7-byte packed decimal, internally (P13)) is comprised of date and time components.  The date portion looks and acts like a D-format variable and the time portion contains a value in the range 00:00:00.0 through 23:59:59.9\. The MOVE EDITED statement (with restrictions) is used to convert D & T variables to and from alphanumeric formats.  

D & T variables can be populated using System Variables, such as *DATX and *TIMX, but literals also may be used.  

D-format literals are specified with 4-digit year, 2-digit month, and 2-digit day. The sequence of the components and the specific delimiter are session-specific.  You can run a 1-ine Natural program to determine them.  
  WRITE *DATX .  

When I run this program, I see a date in mm/dd/yy format, which tells me that D-format literals must be specified in mm/dd/yyyy format.  

The time component of a T-format variable is represented in hh:mm:ss format, although the precision of the variable is to 10ths of a second. Both the date and time components may be specified together in a single literal.  

D-format: D'04/08/2015'  
T-format: T'13:00:00'      /* 1:00pm  
E-format: E'04/08/2015 13:00:00'  

Calculations  
=========  

Numeric-format variables may be added to or subtracted from D variables to move dates forward or backward.  

Separate date and time compnents may be combined by adding a D variable to a T variable.  

T variabes can be used to contain a duration to move times forward or backward.  

Sample Code  
==========  

DTDIFF  demonstrates how to compute the number of days between two dates  
TMDIFF  demonstrates how to compute the number of days, hours, minutes, and seconds between two times  
TMNEW  demonstrates how a time field can be used to specify a duration (eg 1.5 hours) to be used in calculations
