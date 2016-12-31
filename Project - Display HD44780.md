[Arduino Crystal Tutorial (Arduino.cc)](https://www.arduino.cc/en/Tutorial/HelloWorld?from=Tutorial.LiquidCrystal) - very good, has wiring schematic

[Arduino: Arduino LCD Tutorial (YouTube)](https://www.youtube.com/watch?v=JDoTn1sLxWQ)

####Pin-Out
<pre>
Pin -> Arduino Function
1   -> VSS (Gnd)
2   -> VDD (+5V)
3   -> Contrast Adjustment - Connect the center tap of a 10k pot connected between Gnd and 5V
           pot pin out, with center pin furthest away:
           - GND
           --- Out -> 3
           - V+
4  ->  12  RS Register Select Input
5  ->  GND R/W Read/Write Signal, normally at GND
6  ->  11  E Enable
7  ->  N/A
8  ->  N/A
9  ->  N/A
10 ->  N/A
11 ->  5  DB4
12 ->  4  DB5
13 ->  3  DB6
14 ->  2  DB7
15 -> R220 ->  VCC(+) (+5V through a current limiting resistor - I used 220ohm)
16 -> GND (-) Gnd

The Arduino connections are as follows for 4 bit parallel:
LCD Pin: Arduino Pin:
 (1) VSS -> GND
 (2) VDD -> +5V
 (4) RS  -> D12
 (5) R/W -> GND
 (6) E   -> D11
(11) DB4 -> D5    (4 bit parallel)
(12) DB5 -> D4    (4 bit parallel)
(13) DB6 -> D3    (4 bit parallel)
(14) DB7 -> D2    (4 bit parallel)
(15) LED(+) -> 220R  -> +5V  (backlighting)
(16) LED(-) -> GND           (backlighting)
</pre>

<pre>
This is an excellent display. I soldered a header on, then plugged the display into a breadboard 
connected to an Arduino Uno, and it lit right up. Contrast is adjustable as others have described. 
Although I am no expert on these things, the connections to the display seem to be the same as the 
numerous on-line examples which I found. If you are having trouble getting this display working, 
then I recommend you look on-line for sample code and wiring instructions and have some fun with it.

PostNote: Thought I would improve the value of this review for beginners by giving a pin listing, 
since none is provided by the seller:
(Disclaimer: I found this online, and it worked for me. You should check for yourself!)

Pin # Function
1 VSS (Gnd)
2 VDD (+5V)
3 Contrast Adjustment - Connect the center tap of a 10k pot connected between Gnd and 5V
4 RS Register Select Input
5 R/W Read/Write Signal, normally at Gnd
6 E Enable
7 DB0
8 DB1
9 DB2
10 DB3
11 DB4
12 DB5
13 DB6
14 DB7
15 LED (+) (+5V through a current limiting resistor - I used 220ohm)
16 LED (-) Gnd

The Arduino connections are as follows:
LCD Pin: Arduino Pin:
RS D12
E D11
DB4 D5
DB5 D4
DB6 D3
DB7 D2

There are two key lines that should be included in your Arduino sketch:

\#include <LiquidCrystal.h> //Makes available the Arduino environment Liquid Crystal Display
Liquid Crystal lcd(12,11,5,4,3,2); //Assigns the proper pin connections (as above) between Arduino 
and the display
