This posting is a continuation of 'DYNAMIC Variable basics'. 
The intent is to provide an understanding of the basics of DYNAMIC Variables in the hope that programmers will be more "comfortable" with their use, and begin to utilize them more than appears to be the case at present.

In 'DYNAMIC Variable basics' we saw how \*LENGTH is affected by MOVE'ing various variables and constants to a DYNAMIC variable.

To be brief, \*LENGTH reflects the "current" physical size of a DYNAMIC variable. As we noted, this size can include trailing blanks.

By contrast, RESIZE, REDUCE, and EXPAND do not impact current physical size, UNLESS, they specify a size smaller than the current physical size (this can only be done via RESIZE and REDUCE).

The programs in this posting will demonstrate what *\LENGTH really indicates, and how RESIZE, REDUCE, and EXPAND may, or may not, impact \*LENGTH.
