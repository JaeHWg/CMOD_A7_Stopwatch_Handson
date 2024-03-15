# CMOD_A7_Stopwatch_Handson 
<br>

## Features
<br>

### Start/Stop Button
Our first feature would be to add a start/stop button to start and stop the stopwatch. <br>
To do this, we used the second button,btn[0], that is prebuilt into the board. We assigned it to a variable pause and added it as an input in clock_tree.v
When the button is pressed momentarily, the pause button change from 0 to 1 for a moment, this changes a variable, flag, in clock_tree.v from either 0 to 1 or 1 to 0.
The flag will then act as a condition for the clock to stop updating or continue updating.()

### Buzzer Notification
Our second feature would be to add a buzzer to beep for 1s at the 2,4,6 and 8 minute mark. <br>
We assigned a buzzer to PIO35 and added it as an input in num_adder.v. When the 7 segment screen input is 0200,0400,0600 and 0800, the variable egg_done will turn from 0 to 1. <br>
Once the egg_done variable is 1 at the respective times, this will turn the buzzer on.
When the time is not at the exact 0200,0400,0600 and 0800 marks, egg_done will turn back from 1 to 0 and the buzzer will turn off.()

### LED Notification
Our third feature would be that we will have 4 leds to start blinking at the different times:- <br>

time 1) 1 minutes/0100 <br>
time 2) 2 minutes/0200 <br>
time 3) 3 minutes/0300 <br>

We assign the leds to PIO36,PIO37,PIO38,PIO39 respectively and added it as an input in num_adder.v. We then made a separate 25Hz from a 500Hz clock for the led to blink in clock_tree.v and added it as an input in num_adder.v. <br>
When the 7 segment screen input is 0200, the variable led1_on will turn from 0 to 1. When it is 0400, the variable led2_on will turn from 0 to 1. When it is 0600, the variable led3_on will turn from 0 to 1. When it is 0800, the variable led4_on will turn from 0 to 1. When the respective ledX_on turns from 0 to 1, this will engage the LEDX_blinkblink_X to flash with accordance of the 25Hz clock.
