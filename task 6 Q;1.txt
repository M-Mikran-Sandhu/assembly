;MUHAMMAD MIKRAN SANDHU
;260

.386
INCLUDE irvine32.inc

.model small
.stack 100h

.data
msg1 DB "Enter a number=",0
msg2 DB "Today is Monday",0
msg3 DB "Today is Tuesday",0
msg4 DB "Today is Wednesday",0
msg5 DB "Today is Thursday",0
msg6 DB "Today is Firday",0
msg7 DB "Today is Satuday",0
msg8 DB "Today is Sunday",0
msg9 DB "Invalid Number.",0
 

.code
	main proc
	back:
		mov edx,offset msg1
		call writestring
		call readint

		cmp eax,1 ;comparing Accumulator with 1
		je monday

		cmp eax,2 ;comparing Accumulator with 2
		je tuesday

		cmp eax,3 ;comparing Accumulator with 3
		je wednesday

		cmp eax,4 ;comparing Accumulator with 4
		je thursday

		cmp eax,5 ;comparing Accumulator with 5
		je friday

		cmp eax,6 ;comparing Accumulator with 6
		je saturday

		cmp eax,7 ;comparing Accumulator with 7
		je sunday 

		cmp eax,8
		jge invalid_num

		cmp eax,0
		jle invalid_num

		monday:
			mov edx,offset msg2
			call writestring 
			exit
		tuesday:
			mov edx,offset msg3
			call writestring
			exit
		wednesday:
			mov edx,offset msg4
			call writestring
			exit
		thursday:
			mov edx,offset msg5
			call writestring
			exit
		friday:
			mov edx,offset msg6
			call writestring
			exit
		saturday:
			mov edx,offset msg7
			call writestring
			exit
		sunday:
			mov edx,offset msg8
			call writestring
			exit
		invalid_num:
			mov edx,offset msg9 
			call writestring
			
			exit

		invoke ExitProcess, 0
	main endp
end main