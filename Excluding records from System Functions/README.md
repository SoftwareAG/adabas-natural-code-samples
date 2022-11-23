## Excluding Records from System Functions

A simple way to exclude records from System Functions (like SUM, etc).

Many programmers are unaware when System Functions are computed. This leads to their writing code when Natural has facilities to render such code unnecessary.
 
Suppose I have code like the following
```bash
    READ .....
        process record
        AT END OF DATA
            WRITE SUM (SALARY)
        END-ENDDATA
    END-READ
```

As coded above, every record read will be included in the SUM. This happens when an iteration of the READ loop concludes.
There are two ways to cause a loop iteration to end before the loop concludes (thus causing a record to not be included in System Functions).
This program shows both ways (ACCEPT/REJECT and IF....ESCAPE TOP). 
Functionally, the two approaches are identical. Anything that can be done with one can be done with the other.

I tend to prefer using IF...ESCAPE TOP. 
I find it easier for people to understand the code, and, I have witnessed first hand the fact that many Natural programmers do not know all the nuances of ACCEPT/REJECT.
