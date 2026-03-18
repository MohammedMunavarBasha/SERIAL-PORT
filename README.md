
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

ORG 00H 

MOV TMOD,#20H 

MOV TH1,#0FDH 

MOV SCON,#50H 

SETB TRl 

MAIN: 

MOV SBUF,#'B' 

WAIT: 

JNB TI,WAIT 

CLR TI 

SJMP MAIN 

END

### (ii) Serial Port to Transfer a Message

#include<reg51.h> 

void main(void) 

{ 

unsigned char msg[]="Michael"; 

unsigned char i; 

TMOD=0X20; 

TH1=0XFA; 

SCON=0X50; 

TRl=l; 

for(i-0;i<=12;i++) 

{ 

SBUF=msg[i]; 

while(TI==0); 

TI=0; 

} 

while(l); 

}

### OUTPUT:

<img width="957" height="587" alt="image" src="https://github.com/user-attachments/assets/ee4a1aa5-944e-4777-8534-c52a2aa8fb99" />

<img width="999" height="621" alt="image" src="https://github.com/user-attachments/assets/75522c87-1afa-4fa1-8951-2252bfa63219" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
