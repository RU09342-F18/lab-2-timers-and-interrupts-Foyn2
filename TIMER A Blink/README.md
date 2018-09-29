# TIMER A Blink
In the last lab, we were controlling the frequency of the LEDs through use of for and while loops, while also manually delaying the cycles of them. The Timer blink introduces us to a way to control the clock speed internally by setting up values and parameters within (or setting up an interrupt). One of the values that is set within is the capture control register (CCR0). THe CCR0 register would be set to a count limit. Once the timer reaches that count limit value, the interrupt flag would be cleared and the CCR0 would reset. The timer would then count back up to the set CCR0 value, reset, and repeat the cycle. This reset and repeat cycle is how the LED is turning on and off. Setting up two CCR0 registers to be different allows for two LEDs to have separate clock frequencies. This is all done without having to manually delay the cycle.

The G2553 and FR2311 pin assignments had to be different in the code implementation. The code below is how the clocks were set to UP mode (counting upward from 0 instead of from a set number down to 0). The FR2311 had the letters TBCTL and TBSSEL instead of what is seen below (for the G2553

```c
TA0CTL = TASSEL_1 + MC_1;
```
