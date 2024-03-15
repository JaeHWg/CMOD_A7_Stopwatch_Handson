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
Our second feature would be to add a buzzer to beep for a period of 3 seconds as a periodic frequency of 25Hz at the 1,2 and 3 minute mark. <br>
We assigned a buzzer to PIO35 and added it as an input in num_adder.v. When the 7 segment screen input is 0100,0200 and 0300, the variable egg_done will turn from 0 to 1. <br>
Once the egg_done variable is 1 at the respective times, this will turn the buzzer on.
When the time is not at the exact 0100,0200 and 0300 marks, egg_done will turn back from 1 to 0 and the buzzer will turn off.()

### LED Notification
Our third feature would be that we will have 3 leds to start blinking at the different times:- <br>

time 1) 1 minutes/0100 <br>
time 2) 2 minutes/0200 <br>
time 3) 3 minutes/0300 <br>

We assign the leds to PIO07,PIO14,PIO22 respectively and added it as an input in num_adder.v. We then made a separate 25Hz from a 500Hz clock for the led to blink in clock_tree.v and added it as an input in num_adder.v. <br>
When the 7 segment screen input is 0100, the variable led[1] will turn from 0 to 1. When it is 0200, the variable led[2] will turn from 0 to 1. When it is 0300, the variable led[3] will turn from 0 to 1. When the respective led[X] turns from 0 to 1, this will engage the LEDX_blinkblink_X to flash with accordance of the 25Hz clock.

### Picture of set-up
![photo_2024-03-15_16-32-41](https://github.com/JaeHWg/CMOD_A7_Stopwatch_Handson/assets/94187124/e353dfd3-cc47-4420-81fc-ff9a11447488)

### Challenges Faced
Coding the egg timer proved to be a challenge to our team. Firstly, assigning variables and determining the appropriate array size was difficult, because we wanted to implement various time intervals to accommodate different egg doneness. 
<br>
Additionally, we had trouble coding the test bench to verify the functionality and accuracy of the timer. It also took us some time to figure out the desired clock frequency for our timer.
<br>
Another challenge arises from misunderstandings about the power output of the CMOD A7, which can lead to mistakenly believing that the code is not functioning correctly. 
<br>
All in all, Verilog itself poses a challenge due to its unique syntax and structure, making it rather different from other programming languages. Nevertheless, with the help of our professor and TA we overcame these challenges.


