;MUHAMMAD MIKRAN SANDHU
;260
.386
INCLUDE irvine32.inc

.model small
.stack 100h

.data
msg1 DB "Enter a number=",0
msg2 DB "GRADE IS A",0
msg3 DB "GRADE IS B",0
msg4 DB "GRADE IS C",0
msg5 DB "GRADE IS D",0
msg6 DB "GRADE IS F",0
msg7 DB "Your input number is not correct",0

.code
	main proc
	back:
	invalid_input:  ; jump
		mov edx,offset msg1
		call writestring
		call readint

		cmp eax,100 ;comparing Accumulator with 100 error
		jg invalid_num

		cmp eax,90 ;comparing Accumulator with 90 A
		jge gradea

		cmp eax,80 ;comparing Accumulator with 80 B
		jge gradeb

		cmp eax,70 ;comparing Accumulator with 70 C
		jge gradec

		cmp eax,60 ;comparing Accumulator with 60 D
		jge graded

		cmp eax,0
		jle invalid_num

		cmp eax,60 ;comparing Accumulator with lees then 60 F
		jl gradef

		cmp eax,0
		jle invalid_num

		gradea:
			mov edx,offset msg2
			call writestring 
			exit
		gradeb:
			mov edx,offset msg3
			call writestring
			exit
		gradec:
			mov edx,offset msg4
			call writestring
			exit
		graded:
			mov edx,offset msg5
			call writestring
			exit
		gradef:
			mov edx,offset msg6
			call writestring
			exit
		 
		invalid_num:
			mov edx,offset msg7 
			call writestring
			call crlf
			jmp invalid_input
			exit

		invoke ExitProcess, 0
	main endp
end main