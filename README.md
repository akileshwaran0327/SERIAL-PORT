SKILL ASSESMENT-2
## AIM
Write an assembly language program in 8051 to generate a 500 µs delay using Timer 0 in Mode 2 and toggle Port 1.3.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM
ORG 0000H
MAIN: 
MOV TMOD, #02H      
MOV TH0, #06H       
SETB TR0            
AGAIN:
JNB TF0, $         
CLR TF0             
JNB TF0, $          
CLR TF0
CPL P1.3           
SJMP AGAIN         
END

### OUTPUT:
![WhatsApp Image 2025-10-25 at 08 49 15_b38b645e](https://github.com/user-attachments/assets/8937ae01-b272-4df9-8b32-51be7e9f9f84)

### RESULT:
Thus the assembly language program in 8051 to generate a 500 µs delay using Timer 0 in Mode 2 and toggle Port 1.3 is shown.
