Natural developers automatically think READ/FIND when master and transaction files are involved, but a sequential match may be a better solution, dramatically improving performance.

Verify parent-child and child-parent relationships in a single pass.

When processing large master and transaction files, the nested FIND (or READ) is initiated many times. 
Because there is much more overhead involved in starting a FIND than there is in continuing a READ, READing an entire file is much less expensive than FINDing each individual record. 
A sequential match replaces the nested FIND with a READ WORK. The WORK file is created with a READ LOGICAL or PHYSICAL, which will benefit from Prefetch or Multi-fetch.

If you need to find widows (masters with no transactions), you READ MASTER with a nested FIND TRANSACTION. 
Then to find orphans (transactions with no master), you READ TRANSACTION with a nested FIND MASTER. 
The results require two complete passes of the two files. 
Another benefit of a sequential match is that you can find all widows and orphans in a single pass (by Adabas) of each file.

In Natural, a sequential match is implemented with two WORK files, or an ADABAS master with a WORK file for the transactions. 
It may be necessary to flatten an Adabas file to a WORK file. 
A Prefetched READ PHYSICAL as an extract, followed by a sort, will perform very well for this.

It is necessary that the two files be read in the same sequence, and that there is a 1-to-1 or 1-to-many relationship; a many-to-many relationship is not supported. 
In a one-to-many relationship, the master is defined as the 'one' and the transaction file is the 'many'.

For testing/validation purposes, the code is ready to RUN, as is, on mainframe or LUW. 
Follow the embedded instructions for customization for real-world applications. 
A fair bit of the code is for demonstration purposes (e.g. IF #TRACE-xxx ...) and can be deleted once you are convinced the program is working as expected.

Here is my Master test file:

```bash
00000050BOSTON              FRANK               202 555 1212   ACCTNGENG 

00000060SMITH               JOHN                714 555 9876   ENTMNTGER  00000065SMITHERS            CAROL               229 555 1212   ENTMNTENG  00000070SMYTHE              JON                 562 555 6543   ENTMNTGER  00000080GERSTNER            LOU                 204 555 2345   SALE01FRE  

00000090SMITH               SAM                 415 555 6382   SALE01ENG  00000001CAIN                ABLE                800 555 1234   TECH01ENG 
```

Here is my Transaction test file:

```bash
SMITH               ENTMNT07290000025000 

SMYTHE              ENTMNT00284000059900  

GERSTNER            SALE0100185000025000  

GERSTNER            SALE0102974100000000  

GERSTNER            SALE0103297001500000  

GERSTNER            SALE0104126800750000  

HENDRIX             SALE0101184000100000  

SMITH               SALE0100039701000000  

CAIN                TECH0101343000100000  

SMITH               TECH0127032000085500  

THOMPSON            TECH0100719000785000  

THOMPSON            TECH0124900000456700  

ZILDJAN             TECH1300020000012500 
```
                                                        