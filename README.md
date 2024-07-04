# basic-robot-walking-algorithm

a simple algorithm to operate a servo motor for a walking robot can be done by first choosing the number of servos

I choose 4 servos, 2 in the first leg and 2 in the second one 

then I designed a basic mechanism for one leg 


![Image (6)](https://github.com/FaisalBaqutyan/basic-robot-walking-algorithm/assets/174335196/cdb1e990-2eb3-4aa7-83c1-fa77942f8abe)

this mechanism will be applied to the second leg as well

first, the legs will be in the initial position then to move the robot the servo will lift the first leg, then go back to the initial position, then lift the second leg, and go back to the initial position and this mechanism will be applied sequentially 

here I write a simple Arduino code to explain the mechanism 

```
#include <Servo.h>


Servo leftHip;     
Servo rightHip;    
Servo leftKnee;     
Servo rightKnee;    

// i will connect the servos to these pins
const int leftHipPin = 9;
const int rightHipPin = 10;
const int leftKneePin = 11;
const int rightKneePin = 12;



void setup() {
 // put your setup code here, to run once:
 leftHip.attach(leftHipPin);
 rightHip.attach(rightHipPin);
 leftKnee.attach(leftKneePin);
 rightKnee.attach(rightKneePin);

 // initial position 
 leftHip.write(90);
 rightHip.write(90);
 leftKnee.write(90);
 rightKnee.write(90);

 delay(500);
}

void loop() {
  // put your main code here, to run repeatedly:


  // Left leg forward
 leftHip.write(120);
 delay(500); 
 leftKnee.write(60);
 delay(500); 
 leftHip.write(90);
 delay(500); 
 leftKnee.write(90);
 delay(500);

 // Right leg forward
 rightHip.write(120);
 delay(500); 
 rightKnee.write(60);
 delay(500); 
 rightHip.write(90);
 delay(500); 
 rightKnee.write(90);
 delay(500);


}
```

