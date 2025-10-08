# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include <reg51.h>

void main(void)
{
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;

    SBUF = 'A';
    while(TI == 0);
    TI = 0;

    while(1);
}


```
### (ii) Serial Port to Transfer a Message

```
#include <reg51.h>
void main(void)
{
    unsigned char msg[] = "TARUN";
    unsigned char i;
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }

    while(1);
}
```

### OUTPUT:
![serial A](https://github.com/user-attachments/assets/b88270de-5761-47f9-a49a-bd815024238d)


![serial](https://github.com/user-attachments/assets/d51dd9a6-20d9-4de4-af15-2263097d26ec)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
