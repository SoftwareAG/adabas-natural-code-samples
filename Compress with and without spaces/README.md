## Compress with and without spaces

The program compresses values into a text whereby the values are sometimes separated by blanks and sometimes not.
Normally you need multiple COMPRESS statements for this task, some with the "LEAVING SPACE" option and some with the "LEAVING NO SPACE" option.
The program shows how you can compress these value with just one COMPRESS statement.

The trick is to define a binary (B1) field containing a blank character. Because the field is defined as binary, the "COMPRESS LEAVING NO SPACE" is not compressing it.

The code works on all platforms.
