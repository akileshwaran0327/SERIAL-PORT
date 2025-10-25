# SKILL ASSESMENT-1

## AIM
Write an assembly language program in 8086 to check whether a given  number is a palindrome or not. 
## APPARATUS REQUIRED
- Personal Computer  
- DosBox Software  

## PROGRAM
```
DATA SEGMENT
    NUM DW 12321         
    MSG1 DB 0DH,0AH,'Number is Palindrome$'
    MSG2 DB 0DH,0AH,'Number is Not Palindrome$'
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA

START:
    MOV AX, DATA
    MOV DS, AX

    MOV AX, NUM      
    MOV BX, AX       
    MOV CX, 0        
    MOV DX, 0

REVERSE:
    MOV DX, 0        
    MOV SI, 10
    DIV SI           
    PUSH DX          
    INC CX           
    CMP AX, 0
    JNZ REVERSE

    MOV AX, 0
    MOV SI, 1        

REBUILD:
    POP DX           
    MOV BX, DX
    MUL SI           
    ADD AX, BX       
    MOV BX, SI
    MOV SI, 10
    MUL SI           
    MOV SI, AX
    MOV AX, 0
    LOOP REBUILD

    MOV DX, NUM
    CMP DX, SI
    JNE NOTPAL

PAL:
    LEA DX, MSG1
    MOV AH, 09H
    INT 21H
    JMP EXIT

NOTPAL:
    LEA DX, MSG2
    MOV AH, 09H
    INT 21H

EXIT:
    MOV AH, 4CH
    INT 21H

CODE ENDS
END START
```

### OUTPUT:
<img width="616" height="181" alt="image" src="https://github.com/user-attachments/assets/f605240c-f07b-4a70-a90c-2d08c6f23826" />


### RESULT:
thus the assembly language program in 8086 to check whether a given  number is a palindrome or not is shown in output.

