//MUHAMMAD MIKRAN SANDHU//
//          260         //

.386
INCLUDE irvine32.inc

.model small
.stack 100h

.data
msg1 DB "Enter Marks of Subject 1=",0
msg2 DB "Enter Marks of Subject 2=",0
msg3 DB "Enter Marks of Subject 3=",0
msg4 DB "Admission Granted",0
msg5 DB "Sorry,Fail!",0
msg6 DB "Invalid Input! Try Again",0
var1 DD 0
var2 DD 0
var DD 3


.code
	main proc
	back:
	mov edx,offset msg1
	call writestring
	call readint
	mov var1,eax

	mov edx,offset msg2
	call writestring
	call readint
	mov var2,eax

	mov edx,offset msg3
	call writestring
	call readint

	add eax,var1
	add eax,var2
	mov edx,0
	div var
	
    cmp eax,100
	jg inv
	cmp eax,80
	jg suc
	cmp eax,0
	jl inv
	cmp eax,80
	jle fail
	jmp inv

	suc:
	mov edx,offset msg4
	call writestring
	exit

	fail:
	mov edx,offset msg5
	call writestring
	exit

	inv:
	mov edx,offset msg6
	call writestring
	jmp back

	
	

	


		invoke ExitProcess, 0
	main endp
end main