Map a Natural Data Area

Analyse a Natural data area (LDA, PDA or GDA) and build a table of relative field displacements and lengths. Obtained by reading the object's source from FUSER. 
This table may be displayed to show a map of the data area or used for further processing.

The NDA suite comprises: 
|  Name | Description |
|--------------------------|--------------------------|
|  NDATABLE | Subprog to build a table of field offsets for an LDA, GDA or PDA |
|  NDAMAP   |   Program to display this info, showing the start byte and end byte positions for each field |
|  NDAFILE  |    Program to selectively list seq. records defined by an LDA |
|  GDASHOW  | Program to display contents of GDA (calls USR0080N which comes from SYSEXT library) |

Start by stowing NDATABLE and NDAMAP. You should then be able to invoke NDAMAP online or in batch, and get a display of the structure of any Natural data area you provide.
If you have any problems, see first the comments at the top of the code.

**GDASHOW:** 

If you stow this program you can use it to display the contents of your Global Data Area.
Of course, this means you'll need to have an active GDA, so you would be in some application at the time.
Then, if you get to a NEXT prompt (by pressing %% say), then executing GDASHOW and supplying the name of the GDA, you can see its values. There is an option to suppress null value items.
> Note: this utility works by building code in the Editor work area and then running it; so if you wish you can get into the editor and see the source and save it for future use.


**NDAFILE:**

If you have a sequential dataset whose record format is defined by an LDA, you can use this utility to display all or some of those records, formatted according to the field definitions. 
The sample JCL below shows a job to list out (horizontally) 4 fields of the records in 'my.seq.dataset' - Rec-Type, Amount, Cheque-No and Drawee, these being some of the fields in MYLDA. 
The column headings will be Type, Amount, etc. 
Furthermore, the records being selected only those where Record-Type equals 1010, due to the logical operator in col 53 and the value in cols 54-57. 
If you specify selections on multiple fields, they'll be ANDed. 
Finally, the Amount field will be summed, because of the dollar sign in column 53; a total will be printed at the end of the report. Use a plus sign if an integer field. 

```bash
//RSTKDTNF JOB ... 'list selected records' 
//LISTNAT EXEC NATPROC
//CMPRINT DD SYSOUT=X
//CMPRT01 DD SYSOUT=X
//NATT.SYSIN DD *
LOGON RSTKDT
NDAFILE
mylib,mylda,H,0,100
FIN
/* LIBRARY,MEMBER,FORMAT,SKIPRECS,LISTRECS
//*
//* MEMBER: LDA FOR WORK FILE 1
//* FORMAT: V=VERTICAL; H=HORIZONTAL
//* SKIPRECS: NUM RECORDS TO BYPASS
//* LISTRECS: NUM RECORDS TO DISPLAY (0 TO PRINT ALL) 
//CMWKF01 DD *
#RECORD-TYPE Type =1010 
#AMOUNT Amount $ 
#CHEQUE-SERIAL-NO Chq Ser 
#DRAWEE Drawee 
/* --------FIELD NAME----------><-----HEADING------>=<--select value-->
//* LOGICAL OPERATORS: = (EQ), # (NE), > (GT), < (LT), 
//* » (GE), « (LE) 
//* + (sigma count) $ (sigma amount) 
//CMWKF02 DD DSN=my.seq.dataset,DISP=SHR
//
```
