# MPMC-SKILL ASSESSMENT 2

## Aim
To write and execute  an assembly language program in 8051 to generate a 5 second delay using Timer 0 in Mode 1 and toggle Port 2.7 continuously.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software

## Theory 

Timers in the 8051 microcontroller are used to create precise time delays.The 8051 has two timers: Timer 0 and Timer 1.In Mode 1, the timer operates as a 16-bit timer (from 0000H to FFFFH).Each count takes 1 machine cycle = 1.085 µs (for 11.0592 MHz crystal).To create a long delay (like 5 seconds), we repeatedly call smaller delay routines.In this program:

1.Timer 0 is configured in Mode 1 (16-bit mode).

2.A delay of approximately 50 ms is generated each time using Timer 0.

3.This delay routine is repeated 100 times to achieve around 5 seconds.

4.After every 5-second delay, Port 2.7 (P2.7) is toggled (changes state from 0→1 or 1→0).

5.The process continues indefinitely.


## Algorithm
```
Purpose: Toggle P2.7 every 5 seconds using Timer 0.
1.Initialization: MOV P2, #00H sets all Port 2 pins to 0.
2.Call delay subroutine (ACALL DELAY_5S).
3.Toggle P2.7 (CPL P2.7).
4.Repeat (SJMP MAIN_LOOP).
5.Timer 0 in Mode 1 generates small delay.
6.Repeat timer delay 71 times using R2 counter for ~5 seconds.
7.Stop timer and return (RET).
8.Outcome: P2.7 toggles continuously every 5 seconds.
```

## Program

```
ORG 0000H
START:
    MOV P2, #00H
MAIN_LOOP:
    ACALL DELAY_5S
    CPL P2.7
    SJMP MAIN_LOOP

DELAY_5S:
    MOV R2, #71
DELAY_LOOP:
    MOV TMOD, #01H
    MOV TH0, #0BH
    MOV TL0, #00H
    SETB TR0
WAIT_OVF:
    JNB TF0, WAIT_OVF
    CLR TR0
    CLR TF0
    DJNZ R2, DELAY_LOOP
    RET
END
```

## Output

<img width="1657" height="799" alt="image" src="https://github.com/user-attachments/assets/fe40a8da-de76-4407-bd3f-5bfbd1ee9b9f" />


## Result

Thus the program to execute assembly language program in 8051 to generate a 5 second delay using Timer 0 in Mode 1 and toggle Port 2.7 continuously is executed and the output was shown.
