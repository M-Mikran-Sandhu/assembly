.386
INCLUDE irvine32.inc

.model small
.stack 100h

.data
msg1 DB"Enter a Random Number: ",0
var DD 0

.code
	main proc
	mov edx,offset msg1
	call writestring
	call readint
	mov var,eax
	INC var
	call Randomize
	mov eax,var
	call RandomRange
	call writeint

	
		invoke ExitProcess, 0
	main endp
end main