# Button Interrupt
In the previous lab, we did a similar exercise in which we utilized the button to blink an LED on our microprocessor boards. Back then, when we held the button down on the board, the output LED pin would continue to flip between a 1 and 0 (XOR), instead of holding a value. In order to stop that from happening, an interrupt was added shown by the code below.
```c
#pragma vector=PORT1_VECTOR
__interrupt void Port_1(void)
{
}
```
These few lines of code enable the interrupt so that the XORing "freezes" in its tracks, or, as the name implies, interrupts it. In the cases of the two boards, G2553 and F5529, the interrupt would occur when the button is pressed so that the LED would stay on. Once the button is pressed again, the interrupt flag is cleared, turning the LED off. In a way, it works as a basic on/off switch. You press the button, it stays on due to the interrupt. You press the button again, the interrupt flag is cleared and the LED turns off. 

The only difference between the G2553 implementation and the F5529 implementation was that the input/output ports had to be changed. 
