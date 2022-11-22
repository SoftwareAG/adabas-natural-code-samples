Done the "hard way" adding a new occurrence to an MU field as the first occurrence can be CPU intensive, requiring lots of MOVE statements.
This program shows how to do this with just a single MOVE (and some Format Buffer "trickery")

This is a difficult piece of code to understand, hence the in-depth discussion here.

The problem would appear to be quite simple. We have a Multiple Valued field. For our example we will use the LANG field from the Employees file. 
We want to add an occurrence to an instance of the MU field. However, the new occurrence must be added at the beginning of the MU array. That is, it must be the first occurrence of the array.
Why might you want to do this? Suppose the MU field had inspection dates. For every record, more than 90% of the record accesses require solely the most recent (first) inspection date.
 
We will start by discussing the classic way to accomplish our goal. Suppose I have three occurrences of LANG for a record; FRE DUT GER. We wish to add ENG as the new first occurrence. 
The existing three occurrences (currently LANG (1:3)) must slide over and become LANG (2:4) while ENG becomes occurrence 1.
 
How is this usually done? Something like the following:
```bash
FOR #LOOP = C*LANG TO 1 STEP -1 MOVE LANG (#LOOP) TO LANG (#LOOP + 1) END-FOR * MOVE 'ENG' TO LANG (1) UPDATE 
```
As you can see from the code, if there are three existing occurrences, there will be three MOVE's within the FOR loop, plus one MOVE of the new value (ENG). 
Suppose there were fifty occurrences?
Fifty one total MOVE's.
 
Understanding a View
A View in Natural serves two functions. The first is to create what is called a Format Buffer; that is used when calling Adabas to perform read and update functions. 
Format Buffers contain a list of the fields to be read (updated) from a record. 
The second is to create what is called a Record Buffer. This buffer is where values for fields are placed when a record is read from Adabas and where values of fields are placed by a program when it is issuing an update command to Adabas.

In a very real sense, the Format Buffer tells Adabas what fields will be involved in the Command (read, update), while the Record Buffer has the values for the fields. 
Most programmers are familiar with using the Record Buffer. For example, within a READ loop, one might see a statement such as:
```bash
MOVE DEPT TO #ACTIVE-DEPT 
```
which moves a field from the Record Buffer (okay, technically not the Record Buffer) to a user defined variable.

By contrast, very few programmers have ever played with a Format Buffer. Yes, you can do this. In our program we have the following definition within the view MYVIEW:
```bash
02 LANG (#OFFSET:#OFFSET + 5) * ABOVE WILL BE LANG (1:6) FOR READ AND LANG (2:7) FOR UPDATE 
```
As the comment says; by changing the value of #OFFSET, we can basically change the Format Buffer. 
