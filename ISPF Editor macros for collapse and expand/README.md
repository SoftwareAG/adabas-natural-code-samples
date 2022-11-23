## ISPF Editor macros for collapse and expand

Some nice code snippets that can be used with the Natural ISPF *play* command:

Save this code as e.g. *expand* and *collapse* in your natural library (as text members). 
Then assign these text members to PF-Keys, e.g.
* PF15: play collapse
* PF16: play expand

If you are in the editor, press the PF15 key (in my terminal emulation shift-F3) and the source code will collapse and only the lines containing DEFINE SUBROUTINE and DEFINE DATA are shown. 
Then point to the desired subroutine and press PF16 (shift-F4). The subroutine will be expanded. 
You can repeat this as you need (PF15/PF16). 
To reset the display to the entire code enter *RESET* in the command line.
