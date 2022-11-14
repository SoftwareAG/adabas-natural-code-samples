## HISTOGRAM vs READ LOGICAL

You can retrieve data from Adabas' inverted lists, reducing the amount of work Adabas needs to do on your behalf.

**Program 1** uses a READ LOGICAL to retrieve records in a specific sequence and uses BREAK logic to produce counts.  

**Program 2** uses a HISTOGRAM to simplify the logic (eliminates BREAK processing).  All information is retrieved from the inverted lists; no information is retrieved from data records.  Even with the edit mask, the results aren't quite as pretty as in Program 1  

**Program 3** improves the display to match Program 1.
