## READ WORK FILE versus READ WORK FILE RECORD

This sample explains how Natural typically handles Group Names (and Group Array Names).
Then, we explain Natural's one departure from the *typical* handling, namely how they are treated when used in conjunction with READ WORK FILE RECORD.


The first program explains what Group Names (and Group Array Names) really are, namely abbreviations.
There is one exception to the last statement, namely the use of Group Names in a READ WORK FILE....RECORD statement.

There is a significant difference between the following two statements:

```bash
READ WORK FILE 3 ONCE #GROUP (*)

READ WORK FILE 3 ONCE RECORD #GROUP (*)
```
The second and third program explain the difference between these two statements.

