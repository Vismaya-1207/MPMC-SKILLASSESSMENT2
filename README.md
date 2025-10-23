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



## Program








## Output


## Result

Thus the program to execute assembly language program in 8051 to generate a 5 second delay using Timer 0 in Mode 1 and toggle Port 2.7 continuously is executed and the output was shown.
