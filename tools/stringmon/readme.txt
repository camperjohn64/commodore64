STRINGMON is a machine language monitor for the Commodore 64.

To load and run STRINGMON on COMMODORE 64: 
    INSERT OR EMULATE DISK IMAGE FOR STRINGMON

    ; Full verion at $8000    
    LOAD "8000 STRINGMON.1",8,1
    SYS 32768

    ; Condensed verion at $C000
    LOAD "C000 STRINGMON.0",8,1
    SYS 49152

STRINGMON has lots of advanced options like cursor scrolling,
1541 disk memory disassembly, walking through code, sending to 
printer, and even a built in linker for loading 6502 object code.

With the full version, you can even swap out the kernal memory 
on the C64 and view the full C64 memory.

https://github.com/camperjohn64/commodore64/tree/main/tools/stringmon

0. Introduction to STRINGMON Commodore 64 game and source code

John McCarthy attended college night school to learn 6502 
programming in 1982, completing Advanced Assembly Language  
Programming 965 at George Brown College, at the age of 14.

After the Commodore 64, John McCarthy moved on to develop games 
for the PC, as well as 3D game library called 3DVECT39, and then 
worked programming video games for Nintendo, Electronic Arts, 
Atari, and Sony.  

If you find STRINGMON useful and like the source code, please 
consider making a donation to john@mccarthy.net Paypal.

From the source:

;******************************
;**                          **
;**        STRINGMON         **
;**                          **
;**     BY JOHN MCCARTHY     **
;**                          **
;******************************
;
;******************************
;*                            *
;* COMMANDS:                  *
;*                            *
;* ":" ENTER INTO MEMORY      *
;* ";" ENTER REGISTERS        *
;* "R" LIST REGISTERS         *
;* "M" READ MEMORY            *
;* "G" EXECUTE CODE           *
;* "X" EXIT TO BASIC          *
;* "L" LOAD FROM DEVICE       *
;* "S" SAVE TO DEVICE         *
;* "T" TRANSFER MEMORY        *
;* "F" FILL MEMORY            *
;* "H" HUNT FOR VALUES        *
;* "D" DISASSEMBLE CODE       *
;* "," ENTER AND DISASSEMBLE  *
;* "A" ASSEMBLE CODE          *
;* "Q" KILL STRINGMON         *
;* "C" COMPARE MEMORY         *
;* "@" SEND DISK COMMAND      *
;* "E" MAP MEMORY AS TEXT     *
;* ">" ENTER MEMORY AS TEXT   *
;* "K" CONVERT DIGITS         *
 .IFE EXTRAS <
;* "W" WALK THROUGH CODE      *
;* "I" INPUT FROM DISK MEMORY *
;* "O" OUTPUT TO DISK MEMORY  *
;* "]" FLAGS DRIVE READ       *
;* "." FLAGS COMPUTER READ    *
;* "U" SETS UNIT TO MAP       *
;* "P" ACTIVATES PRINTER      *
;* "*" OBJECT LOADER          *
>
;*                            *
;* SUB COMMANDS:              *
;*                            *
;* "$" SET HEX INPUT MODE     *
;* "%" SET BINARY INPUT MODE  *
;* "/" SET DECIMAL INPUT MODE *
;* "@" SET OCTAL INPUT MODE   *
;* """ TOGGLE ASCII INPUT     *
;* ":" FLAG END-OF-INPUT LINE *
;* "+" ADD LOCATIONS          *
;* "-" SUBTRACT LOCATIONS     *
;*                            *
;******************************
;
 .IFE EXTRAS <
;******************************
;*                            *
;* NEW INPUT ROUTINE ADDS:    *
;*                            *
;* CURSOR UP SCROLLING        *
;* CURSOR DOWN SCROLLING      *
;* BLACKHOLE DELETE           *
;* SHIFT RUN PRINTS .L":*     *
;* F1 - GO TO TAB             *
;* F2 - SET TAB               *
;* F3 - CLEAR AFTER CURSOR    *
;* F4 - CLEAR BEFORE CURSOR   *
;* F5 - CLEAR RANGE AFTER CS  *
;* F6 - CLEAR RANGE BEFORE CS *
;* F7 - UPSIDEDOWN HOME KEY   *
;* F8 - ESCAPE KEY            *
;* CTRL "D" TOGGLES DELETE    *
;* CTRL "P" SCREEN DUMP       *
;*                            *
;******************************
;
>
;******************************
;*                            *
;* VERSION 0 SOURCE CODE:     *
;*                            *
;* NORMAL STRINGMON,  THIS IS *
;* A 4K VERSION  THAT HAS ALL *
;* THE   STANDARD   COMMANDS. *
;* THE  KERNAL   INPUT    AND *
;* PRINT  ROUTINES  ARE USED. *
;* KERNAL  TALK   AND  LISTEN *
;* ROUTINES ARE USED FOR DISK *
;* ACCESS, THE  OPEN  ROUTINE *
;* IS USED FOR LOAD AND SAVE. *
;* DISK MODE AND PRINTER MODE *
;* HAVE BEEN TAKEN OUT SO  IT *
;* CAN FIT IN THE  4K  SPACE, *
;* THE WALK COMMAND HAS  ALSO *
;* BEEN REMOVED.              *
;*                            *
;* VERSION 1 SOURCE CODE:     *
;*                            *
;*   MATCHES  VERSION ONE BUT *
;* WITH THESE "EXTRAS": A NEW *
;* INPUT ROUTINE HAS BEEN PUT *
;* IN  WITH   A   NEW   PRINT *
;* ROUTINE, THESE ROUTINES NO *
;* LONGER USE THE VECTORS FOR *
;* THE KERNAL INPUT AND PRINT *
;* INPUT SCROLLING,  FUNCTION *
;* KEY STUFF, DISK  MAP  MODE *
;* DISK INPUT AND  OUTPUT  OF *
;* CODE,   CODE  WALKING  AND *
;* PRINTER   MODE  HAVE  BEEN *
;*   ADDED TO THIS VERSION.   *
;*                            *
;******************************
;
