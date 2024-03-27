These functions do the same as PL/1 functions "SEARCH()" and "VERIFY()". 
SEARCH(P_STRING, P_SEARCH) will return the position of the first character in P_STRING which can be found in P_SEARCH. 
VERIFY(P_STRING, P_VERIFY) will return the position of the first character in P_STRING which does NOT occur in P_VERIFY. 

There three sets of two functions and one demo program, once for type A, once for B, and once for U:

FxSEARCH -> Function SEARCH()
FxVERIFY -> Function VERIFY()
PxVERIFY -> Demo program calling both FxSEARCH and FxVERIFY
x = A, B or U

All parameters and results are DYNAMIC, which allows flexible work.
