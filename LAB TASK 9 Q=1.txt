;MUHAMMAD  MIKRAN SANDHU
;BSCS III F

;QUESTION : 1



.386
include irvine32.inc
.model small
.stack 100h

.data
msg db "Enter A starting number:",0						;msg 
msg1 db "Enter A ending number:",0						;msg 

startt dd 0
endd dd 0
rangee dd 0
dod dd 2

.code
     main proc

     mov edx, offset msg 				;msg print
     call writestring					 

     call readint 

     mov startt,eax
     
     mov edx, offset msg1 				;msg print
     call writestring

     call readint 

     mov endd,eax

     sub eax,startt					;range
     
     mov rangee,eax

     mov ecx,rangee
     inc ecx						;increment

     count:						;loop
        mov edx ,0
        mov eax,startt

        div dod

        cmp edx, 0
        je yess
        jne noo


        yess:
        
            mov eax,startt				;print even
            call writeint
            call crlf
        noo:

            INC startt					;increment


        loop count



 invoke exitprocess,0

 main endp
 end main