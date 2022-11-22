This code sample adds **Case 4** to Steve Robinson's post "Eliminating Special Characters from String".
From the fertile imagination of Paul Macgowan.

**Case 5** added April 11, 2015.    

Case 4 works as follows:
* Replace all "candidate characters" with a single known value, using EXAMINE TRANSLATE.
* Delete all the "known values" from step1, using a single EXAMINE DELETE.

Case 4 is slightly quicker than Case 3.

> Note:
We felt that Case 3 was cheating slightly because the EXAMINE DELETEs had nothing to replace after the first iteration.
In Case 3 we inserted "RESET INITIAL #A" into the loop to force each DELETE to "do something".
So in fairness, "RESET INITIAL #A" was inserted into all of the other loops too, including the "empty loop" to get a good baseline comparison.
In the "empty loop" IGNORE was replaced by "RESET INITIAL #A" (just in case IGNORE consumes any CPU).
Thanks to Paul Macgowan for this solution.

**Amended April 11, 2015**
The latest Natral releases allow for a single EXAMINE for multiple strings.  This reduces CPU by another 30%.  See Case 5.
I eliminated the line numbers from the code to allow for cut & paste.