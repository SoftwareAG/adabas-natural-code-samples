This posting contains two programs. 
* The first demonstrates two techniques for eliminating null occurrences from an array. 
* The second program shows a timing comparison between the two techniques.

The second technique shown (the EXAMINE technique) is significantly more efficient than the first technique (the COMPRESS technique).
The EXAMINE does require that the array be made a part of a Group Array. 
This will not change the accessibility of the array, hence will not require program changes, UNLESS, you require a REDEFINE of the array into a single string. The "divider characters" (I used an ampersand) would "interfere" with the array string. This would require additional programming changes.
