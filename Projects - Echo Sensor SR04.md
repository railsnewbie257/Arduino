[Ultrasonic Sensor HC-SR04 and Arduino Tutorial (YouTube)](https://www.youtube.com/watch?v=ZejQOX69K5M)

<pre>
Pinout:

<b>SR04</b>       <b>Arduino</b>
VCC   -->  +5V  
Trig  -->   10   
Echo  -->    9   
GND   -->  GND   
</pre>

Arduino IDE Sketch
<pre>
const int trigPin = 9;
const int echoPin = 10;

long duration;
int distance;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(115200);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034/2;

  Serial.print("Distance: ");
  Serial.println(distance);
}
</pre>
