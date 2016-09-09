These are bare temperature and humidity sensors. They are pinned Vcc, Data, NC (no connection), Gnd. They give readings roughly once per minute and are fairly accurate as they are factory calibrated. The main difference between this sensor and the 3 pin circuit board mounted versions is 
<pre>
<b>this sensor requires a 5K ohm pull-up resistor on the data line</b>
</pre>

which the circuit board mounted version provides. To state this more clearly, to use this bare sensor you must add a 5K ohm resistor between pins 1 (Vcc) and 2 (Data) as per the manufacturers specification. Not a big deal given all four of these are less expensive than a single circuit board mounted sensor. (from [here](https://smile.amazon.com/Digital-Humidity-Temperature-Sensor-Arudino/dp/B007YE0SB6/ref=sr_1_1?s=hi&ie=UTF8&qid=1473400490&sr=1-1&keywords=dht-11#customerReviews))


###DHT11 Pinout (from 37 Sensor Kit)
<pre>
3 Pin Breakout:
S   -> signal, Arduini pin 8 (for this sketch)
VCC -> +5V
GND -> GND
</pre>

See setup for LCD display 

###[Geeetech Wiki Page](http://www.geeetech.com/wiki/index.php/Electric_thermometer_by_using_DHT11_sensor_module)

###Modified Sketch for DHT11
<pre>
#include "DHT.h"
#include <LiquidCrystal.h>
#define DHTPIN 8   
#define DHTTYPE DHT11
DHT dht(DHTPIN, DHTTYPE);
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
void setup() {
Serial.begin(9600);
lcd.begin(20, 4);
dht.begin();
lcd.print("Setup");
}
void loop() {
float h = dht.readHumidity();
float t_c = dht.readTemperature();
float t_f = dht.readTemperature(true);
if (isnan(t_c) || isnan(t_f) | isnan(h)) {
  Serial.println("Failed to read from DHT");
  }
else {
  lcd.setCursor(0,0);
  lcd.print("Temp=");
  lcd.print(t_f);
  lcd.print("F  ");
  lcd.print(t_c);
  lcd.print("C");
  lcd.setCursor(0,1);
  lcd.print("Humidity=");
  lcd.print(h);
  lcd.print("% ");
  delay(500);
 }
}
</pre>


[DHT11 Tutorial (Brainybits.com)](https://brainy-bits.com/tutorials/dht11-tutorial/)

[Portable Arduino Temp/Humidity Sensor with LCD](https://create.arduino.cc/projecthub/ThothLoki/portable-arduino-temp-humidity-sensor-with-lcd-a750f4)

[Manufacturer 3-Pin Wiki](http://www.geeetech.com/wiki/index.php/Electric_thermometer_by_using_DHT11_sensor_module)

[DHT11 GitHub Repository](https://github.com/adafruit/DHT-sensor-library/blob/master/examples/DHTtester/DHTtester.ino)

[Basics with DHT11 (stackexchange)](http://arduino.stackexchange.com/questions/4667/basics-with-dht11?newreg=39b1e36be038464fbb2e5684dc12993d)
