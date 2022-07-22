# Hand Washer Timer
The hand washer timer is a contactless timer which, when activated, times the user for 20 seconds as they wash their hands, and upon completion emits a sound to notify the user that they can stop washing their hands. It uses a SuperSonic Sensor in front of which the user places their hands to start the timer. Additionally, after the 20 seconds elapse, a buzzer will sound. 

<p align = "center">
<a href="https://ibb.co/rwz22pD"><img src="https://i.ibb.co/tJvpp2V/IMG-20220718-093944.jpg" alt="IMG-20220718-093944" border="0" height="700" width = "570"></a><br />
</p>

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Parav M.| Saratoga Highschool | STEM | Incoming Junior

# Picture of Finished Project
<p align = "center">
<a href="https://ibb.co/41gj0Z8"><img src="https://i.ibb.co/fDGCTYk/IMG-20220715-102114.jpg" alt="IMG-20220715-102114" border="0" height="380" width = "570"></a><br />
</p>

# Third Milestone
My third milestone was creating my presentation and finally putting the entire project together. I added the buzzer which continued for the entire 20 second duration, and only emitted sound when the sensor detected an object in front of it. When the last LED blinks, the uniform buzzing noise segments into isolated blinking sounds in succession, indicating the completion of the timer.   

[![Milestone 3](https://res.cloudinary.com/marcomontalbano/image/upload/v1658422902/video_to_markdown/images/youtube--RfLe5IRrhvs-c05b58ac6eb4c4700831b2b3070cd403.jpg)]( https://youtu.be/RfLe5IRrhvs "Milestone 3")

# Second Milestone
My second milestone was the 4 LED’s which represented the increments of time elapsing after the sensor was activated. Additionally, the code was updated to have the sensor detect an object within the range of 1 - 50 cm in front of it. The resistors used for the LED's bottleneck the flow of the current, as only a certain amount is needed for each of them. For the next milestone, I will add the buzzer to which will make a sound when the sensor is activated. 

[![Milestone 2 ](https://res.cloudinary.com/marcomontalbano/image/upload/v1657819855/video_to_markdown/images/youtube--J1Wg8NqKBLo-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/J1Wg8NqKBLo "Milestone 2 ")

# First Milestone
  
My first milestone was the sensor and buzzer, one of the most important functional components for the project, since it allows one to activate the timer, and to have it produce the sound which indicates said activation, in a contactless fashion. In the code, the SuperSonic Sensor will only detect an object in front of it from a range of 5 to 20 cm inclusive. So if one were to place an object directly in front of it, which would basically be 0 cm away, there is no detection, and likewise, if one were to go more than 20 cm away from it, there would also be no detection. Through the wiring, the code is being passed into the arduino, the arduino provides the current, the current then passes around to all of the components on the breadboard, so that both the LED and the buzzer will activate simultaneously when the sensor does. The resistor regulates the flow of the electrical current in the circuit.

[![Milestone 1 (Parav)](https://res.cloudinary.com/marcomontalbano/image/upload/v1657557884/video_to_markdown/images/youtube--G_ayPi7pqe0-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=G_ayPi7pqe0 "Milestone 1 (Parav)")

# Bill of Materials 

This is a table containing all the items needed for the project. It contains the item, quantity, price, and where to buy the item.

| Item | Qty | Price | Where to Buy |
| ------------- | ------------- | ------------- | ------------- |
| Breadboard  | 1 |  $6.75  | https://www.amazon.com/BB400-Solderless-Plug-BreadBoard-tie-points/dp/B0040Z1ERO |
| Jumper Wires  | 6 | 10¢/wire  |  https://www.amazon.com/Breadboard-Jumper-Wire-75pcs-pack/dp/B0040DEI9M |
| Arduino Uno Board  | 1  | $27.60  | https://store-usa.arduino.cc/products/arduino-uno-rev3?selectedStore=us  |
| Arduino IDE  | 1  | $0  | https://www.arduino.cc/en/software/ |
| LED | 5 | $3.05 |https://www.amazon.com/DiCUNO-450pcs-Colors-Emitting-Assorted/dp/B073QMYKDM/ref=sr_1_3?crid=6LJDAI89J5SQ&keywords=LED+kit&qid=1653586560&sprefix=led+kit%2Caps%2C175&sr=8-3 |
| UltraSonic | 1 | 3.95 | https://www.digikey.com/en/products/detail/adafruit-industries-llc/3942/9658069?utm_adgroup=Temperature%20Sensors%20-%20NTC%20Thermistors&utm_source=google&utm_medium=cpc&utm_campaign=Shopping_Product_Sensors%2C%20Transducers_NEW&utm_term=&utm_content=Temperature%20Sensors%20-%20NTC%20Thermistors&gclid=Cj0KCQjw8uOWBhDXARIsAOxKJ2GRJr-YuEC5TYBnVz52mJ3fxJ0dQcGTH9WjiTcOlsTtiYiEeHZa5gUaAh4VEALw_wcB |

# Schematic

<p align="center">
<a href="https://imgbb.com/"><img src="https://i.ibb.co/CsrdRQq/schematic.png" alt="schematic" border="0"></a>
</p>

# Steps to Recreate the Project
Use the bill of materials above to obtain the components of the project. Ideally, each LED should have a distinct color. One of these LED's should be used as the start, which blinks upon the timer's activation. Put the SuperSonic sensor, the LED's, and buzzer, on Breadboard as shown in the project image. Use the schematic above to wire the the main components. Make sure that the sensor detects the object in front of it from a range of 1 - 30 cm inclusive, that the starting LED momentarily lights up, and that, afterwards, the row of the remaining four LEDs light up in succession for every 5 second interval. 


# Code for processing

```
#define trigger 8
#define echo 9
#define buzzer 7
#define LEDstart 10
#define LED5 11
#define LED10 12
#define LED15 13
#define LED20 6

int i=0; 

void setup() {
  // put your setup code here, to run once:
  pinMode(trigger, OUTPUT);
  pinMode(echo, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(LEDstart, OUTPUT);
  pinMode(LED5, OUTPUT);
  pinMode(LED10, OUTPUT);
  pinMode(LED15, OUTPUT);
  pinMode(LED20, OUTPUT);

}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(buzzer, HIGH);
      tone(buzzer,400);
  long duration, dist;
  digitalWrite(trigger, HIGH);
  delay(1000);
  digitalWrite(trigger, LOW);
  duration = pulseIn(echo, HIGH);
  dist = (duration/2)/29.1;
  delay(10);
 if(dist <= 50 && i==0)
 {
  digitalWrite(LEDstart, HIGH);
  delay(5000);
  digitalWrite(LED5, HIGH);
  delay(5000);
  digitalWrite(LED5, LOW);
  digitalWrite(LED10, HIGH);
  delay(5000);
  digitalWrite(LED10, LOW);
  digitalWrite(LED15, HIGH);
  delay(5000);
  digitalWrite(LED15, LOW);
  digitalWrite(LED20, HIGH);
  for (int j=0; j<5; j++)
  {
      digitalWrite(buzzer, HIGH);
      tone(buzzer,400);
      delay(10);
     digitalWrite(buzzer, LOW);
     noTone(buzzer);
     delay(1000);
  }
  digitalWrite(buzzer, HIGH);
  tone(buzzer,400);
  i=1;
 }
 long duration1, dist1;
  digitalWrite(trigger, HIGH);
  delay(1000);
  digitalWrite(trigger, LOW);
  duration1 = pulseIn(echo, HIGH);
  dist1 = (duration1/2)/29.1;
  if (dist1<=50 && i==1)
  {
     digitalWrite(LED20, LOW);
    digitalWrite(buzzer, LOW);
    digitalWrite(LEDstart, LOW);
    i=0;
  }
  
}
```
