//MUHAMMAD MIKRAN SANDHU//
//          260         //

.386
INCLUDE irvine32.inc

.model small
.stack 100h

.data
msg1 DB "Enter a Number: ",0
msg2 DB "Even",0
msg3 DB "Odd",0
var DD 2

.code
	main proc
	mov edx,offset msg1
	call writestring
	call readint
	mov edx,0
	div var
	mov eax,edx
	cmp eax,1
	je od
	cmp eax,0
	je ev

	od:
	mov edx,offset msg3
	call writestring
	exit

	ev:
	mov edx,offset msg2
	call writestring

		invoke ExitProcess, 0
	main endp
end main