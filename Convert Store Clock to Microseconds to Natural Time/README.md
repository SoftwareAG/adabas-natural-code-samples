Convert

* Natural time stamp (store clock) value into microseconds;
* Microseconds into a Natural time (T) value;
* and vice versa

The conversion is performed by the enclosed copycodes. 
The programs are showcases how the copycodes may be used.

**Program TIME-SMT**
Sample program to demonstrate the usage of the time conversion copycodes. It converts timestamps (store-clock) values into microseconds; and microseconds into Natural time (T) values. 
The timestamps are taken at the start and end of the program and the elapsed time of the program is calculated in precision of microseconds. 

**Program TIME-TMS**
Sample program to demonstrate the usage of the time conversion copycodes. It converts a Natural time (T) value into microseconds; and the microseconds into a timestamp (store-clock) value.
 
**Copycode MIS2STCK**
Convert microseconds into a store-clock value.

**Copycode MIS2TIME**
Convert microseconds into a Natural time value.

**Copycode STCK2MIS**
Convert a store-clock value into microseconds.

**Copycode TIME2MIS**
Convert a Natural time value into microseconds.

> **Note:**
The copycodes are platform-independent. The copycodes perform similar functions as the APIs USR1009N and USR1023N. The copycodes are in general faster than the APIs. 
When a Natural time is converted to microseconds with the copycode TIME2MIS, a negativ result can be obtained (dates before 1900). The API returns an error in this case. 

### Statistics
A Natural program converts 1,000,000 times a store-clock value into a Natural time value. The test was running on z/OS and on Windows. 
The values from different platforms should not be compared - my Windows is probably not the best.
In a first run the API is used for the conversion, in the following the copycodes. The API always returns the microseconds, the Natural Time and the Natural date. 
When the store-clock is converted with the copycodes, it is first converted into microseconds (mis) with the copycode STCK2MIS. 
The microseconds are converted into a Natural time value with the copycode MIS2TIME. Finally, if the Natural date is also desired, the Natural time value is moved to a Natural date value. 
Therefore the conversion into microseconds is the fastest if the other formats are not needed.

> **Platform z/OS**
Unit USR1023 Copycode (STCK->mis) Copycode (STCK->mis->T) Copycode (STCK->mis->T->D) CPU seconds 113,95 4,59 6,83 7,61 Factor Usr/CC n/a 24,82 16,67 14,96  
 
> **Platform Windows**
Unit USR1023 Copycode (STCK->mis) Copycode (STCK->mis->T) Copycode (STCK->mis->T->D) CPU seconds 25,50 7,67 10,20 11,36 Factor Usr/CC n/a 3,32 2,50 2,24  
 
The API uses another logic on Windows and UNIX (C-Code) than on the mainframe. Therefore we see the big differences in the platforms.
On Windows (in my tests), the copycode is up to 3.3 times faster than the API; on z/OS it is up to 25 times faster 


### Remark
With Natural 8.3.7 on Windows and UNIX and Natural 8.2.6 on the mainframe, the time conversion APIs USR1009N, USR1023N, and USR2036N have been redesigned and now provide a significantly better performance. 
In addition to the subprograms, the utility SYSEXT provides copycodes for the conversion of time related values: USR1023W/X/Y/Z. 
The copycodes of SYSEXT provide the same functions (and the same performance) as the copycodes described above. 
For more information, see the corresponding Natural release notes.
