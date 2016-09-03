###[Arduino IRremote (website)](http://z3t0.github.io/Arduino-IRremote/)

<pre>
Description:

Infrared sensor type 1838 for use with 38KHz IR signals.
 Supply voltage: 2.7 to 5.5 V
 Frequency: 37.9 KHz
 Receiver range: 18m (typical)
 Receiving angle: 90°
Library: https://github.com/shirriff/Arduino-IRremote
</pre>


[download library IRremote.h here](https://github.com/z3t0/Arduino-IRremote/releases/tag/2.1.0)

<pre>
after installing library you may get this message from the IDE:

Multiple libraries were found for "IRremote.h"
 Used: /Users/peterpih/Documents/Arduino/libraries/IRremote
 Not used: /Users/peterpih/Applications/Arduino.app/Contents/Java/libraries/RobotIRremote

the Arduino.app RobotIRremote can be deleted
</pre>

The example sketch uses PIN 11 as input on Arduino.  
S-out needs a pull-down resistor.   
Chip needs +5V  
The onboard LED should be ON until a signal is received.   


<pre>
Pin out:
G -> GND
R -> +5V
Y -> S-out
  -> 220R -> GND
</pre>
  

###Other useful links (DO NOT USE THE LIBRARIES ! )
[Receiving and Decoding IR (Adafruit)](https://learn.adafruit.com/using-an-infrared-library/hardware-needed)  
[IRLib (Github)](cyborg5/IRLib)

[Testing an IR Sensor]

[Using an IR Sensor (Adafruit)](https://learn.adafruit.com/ir-sensor/testing-an-ir-sensor)

[adafruit/Raw-IR-decoder-for-Arduino (Github)](https://github.com/adafruit/Raw-IR-decoder-for-Arduino/blob/master/rawirdecode/rawirdecodestruct.ino)
