HackOmation2023 - Team LeftOvers
================================

Mecanum Wheelchair


Team members:

Soman Karan, coder

Ziyana Ramdutt, pitcher

Declan

Sarah

 

Day 1 (25/04/2023)

Because of personal reasons, I had left my previous team (Titans) and decided to not participate anymore in HackOmation. On 25th of April 2023 Julie asked me if I wanted to join a new team, which was recently made at that time and I had agreed. The name of our team is "LeftOvers". I don't think the name of our team needs any explanation, because the name itself already says a lot. Our team was given the project "mecanum wheels" by mr. Theo himself and this was before I joined the team and before anyone had started to work on this project, so I joined at the right time.

Important note

Our team consists only of members of the Innostarter 6th Edition, because members of the innostarter were not obligated to participate in HackOmation, so only 4 members decided to participate in HackOmation.

Day 2 (26/04/2023)

The next day our team came to the lab to discuss some ideas about our project. We discussed how the mecanum wheels could be used in a helpful way.  And we decided that our project will be a wheelchair with mecanum wheels. Not a literal wheelchair, but the prototype should represent a wheelchair. We came up with the idea that we could just make a rover with 4 mecanum wheels and on top of the rover we'll place a seat of which the leaning could also be adjusted for the patient's comfort.

Important note

As members of the innostarter, we came to the lab every week on wednesday and on the same day we also discussed a little about our project.

Day 3 (28/04/2023)

We discussed the parts that will be used for our project and if our project will be controlled via wifi or bluetooth. We came to the conclusion that we'll decide in the near end of our project if we'll control our project via bluetooth or wifi.

The needed components for now:

-   Arduino nano

-   Breadboard

-   4 dc motors

-   2 L298N modules

-   Jumper wires

-   A battery pack

Important notes

We were advised to first try to make our project work with an arduino nano, as seen that it's quite a difficult project, then we should try to make our project work with the esp32.

Pictures:

-   Sorting our components so that we have an image of how big the base of our project should be.

            ![](https://lh5.googleusercontent.com/-ouKYwOg4yRXwNZjM3nU8QNFnLIX3DlqL1cbxUi3SbNIiLWHrh2xDuobGtGxq3tEqkPL_mUXZQgZgxR2RuELnr8BdeLb-BY06rUIfViBSd8estGO7FQwM74CRW1F0WWpXrE22zikCgAoBHxmjTJV8o8)

-   The same day a team member made a 3D design of our project on tinkercad. The body of our project will have a thickness of 3mm, height of 45mm, width of 180mm and a length of 280mm.

![](https://lh5.googleusercontent.com/DhaXqpyWqNZ9_9y73C26JF6u_KNcWcwyzT5HB8EIvCk8liRLu8LQFsCH2lnOjkGEvFS6Nb6ACpKPgdRI4jpvvSgyNoiPeCOSjkVMtsdQCRdqt1Jf7sqlRJUjbH7CICEM7-0rPjU633CKjaskNAGyO1M)

Day 4  (03/05/2023)

On this day the coder of our team made a simulation of our project in tinkercad and tried to make each wheel rotate independently. And after a lot of hard work, he finally got the wheels to rotate independently.

Important notes

The coder of our team watched a YouTube video of how the mecanum wheels and how each wheel should rotate to make the rover move in a specific direction. A rover with mecanum wheel can move in 8 different directions, namely; forward, backward, left, right and diagonally (top-right, top-left, bottom-left and bottom-right). The rover can also rotate clockwise and counterclockwise.

Pictures:

-   A sketch of how each motor should rotate to make the rover move in the desired direction.

![](https://lh6.googleusercontent.com/GZiuNrKndk9dsni90BbDPuoBYOeTkYvJMNOT9gdxrGgQQRGcUrjVRNPUiO5N7MD3FBLmdgjAFg4qex8-rLHLfVDAqhn9tqg1rRspZVkgRfRW6fXC1f3DhWKPo1VAw5GJ9x_zKjhcrXICoG8O3xtqeFw)

-   A simulation of our project in tinkercad.

![](https://lh4.googleusercontent.com/FJFn9iwaP0yCWDn5yRBwKrGqstyglAdEdJCFY_Tdav_tE4XE33Yt9jWPPAUjsvbkyJtyhR2u7d9yyi3RU1FFJMKJNNoGz8-PrjgZV7Vw-uKyIgcj840ctvL_MoNoEUOod9GZVI5S3BhPspkNQUZVdSM)

Algorithm:

int motor1enA = 5;

int motor1in1 = 7;

int motor1in2 = 4;

int motor2enB = 3;

int motor2in3 = 6;          

int motor2in4 = 2;

int motor3enA = 10;

int motor3in1 = 8;

int motor3in2 = 12;

int motor4enB = 11;

int motor4in3 = 9;

int motor4in4 = 13;

int state; 

int speed = 255;

void setup()

{

  Serial.begin(9600);

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, speed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, speed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, speed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, speed); 

}

*******************************************************/

void loop()

{

  if (Serial.available() > 0){

    state = Serial.read();

    if (state == 'F'){

      Serial.println("Go North");

      forward();

    } else if (state == 'B'){

      Serial.println("Go South");

      backward();

    } else if (state == 'L'){

      Serial.println("Go West");

      left();

    } else if (state == 'R'){

      Serial.println("Go East");

      right();

    } else if (state == 'N'){

      Serial.println("Go NorthWest");

      leftforward();

    } else if (state == 'n'){

      Serial.println("Go NorthEast");

      rightforward();

    } else if (state == 'Z'){

      Serial.println("Go SouthWest");

      leftbackward();

    } else if (state == 'z'){

      Serial.println("Go SouthEast");

      rightbackward();

    } else if (state == 'r'){

      Serial.println("Rotating right");

      rotateclockwise();

    } else if (state == 'l'){

      Serial.println("Rotating left");

      rotatecounterclockwise();

    } else if (state == 'S'){

      Serial.println("Stop");

      stop();

    }

  }

}

/**************************************************************/  

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void leftforward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rightforward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void leftbackward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rightbackward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void rotateclockwise() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void rotatecounterclockwise() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void stop() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

Day 5  (06/05/2023)

We visited the lab to construct our project for the first time. After connecting the components to their respective parts, we ran the program and it worked without any issues initially. However, the batteries drained very quickly, causing a disruption. Despite this setback, our code functioned flawlessly, and the motors rotated independently as intended.

Important notes

Our batteries ran out of power very quickly, because two 3V batteries is not enough to power two L298N motor driver modules and the arduino nano.

Pictures:

-   Connecting the components to their respective parts. 

![](https://lh4.googleusercontent.com/7JnX8DV7IPgnm55vZjrvgsvUQEoRxcWV7QiywywFdAJ9QwKEb3lvXpUUit3MsIB1EnLUooKK0YQYuplZfc76wO_xciVXYq69QxPmAmQAAOJH-DiK5FNo_5XuOllWbEWCwmko1BgsZpgOHOzsm0hKk9c)

Algorithm:

We used the same algorithm, which is written on the algorithm section on day 5.

Mistakes

-The mistake we made is not considering the fact that our project would require more power.

-We screwed all the wires that had to be connected to both of the L298N motor driver modules, tightly, not realizing that we might need to unscrew the parts later in the future.

Day 6  (10/05/2022)

A team member sent mr. Theo the svg file, which consisted of the 3D design of the body of our project (created in tinkercad), which had to be lasered. But he forgot to check the file.

Pictures:

-   The parts which had to be lasered for our project.

![](https://lh3.googleusercontent.com/skswz0H8y1CTsNDxYkTUDoz-hcIycT2W3v8rXu9J_BiyhB42dFZWzS4IfpI8hwSd_FCLODpUiukwsca26_YuW7Jq3L65v9mVbLQDmwpsLjWo5Mn65J_xXJzT-pE-ykir8s3Nnv54Xw7_c4BEI5XkmSs)

Day 7  (14/05/2022)

The coder of our team gave mr. Theo and Julie a reminder that our team hadn't gotten an ESP32 yet (they forgot that they hadn't given us an ESP32 yet) and that our rovers body had to be lasered, but they were not able to give it to us, because they would be out of the city for 3 days and were going to be back on the  18th of may.

Day 8  (19/05/2022)

Karan went to the lab and got the ESP32 and the lasered parts for our rover.

Day 9  (20/05/2022)

Karan and Ziyana went to the lab and they wanted to test how the ESP32 actually works before they started working with it for our project. So they tried to get this project, "ESP32 Web Server (WebSocket) with Multiple Sliders" to work, so that they would understand how the ESP32 works. And they got it to work.

Pictures:

-   The project they tried to do and succeeded  

           ![](https://lh6.googleusercontent.com/SQ8I2cKtUvG-dvcvT3RUDo4_uFd5-jeAKoiSq2oJxwqPxYeLk4q9HdRYqttvOBYYLm-I-Ch46lHDBe7s9tXrBQ8gRomatnsLXOHrJDUJbli7x9rq0NqIMbchHcneOepC9HXb2TrfDYUK7kk6BTmLYfA)

Day 10  (25/05/2022)

Our programmer connected the components to the ESP32 and tried to make the wheels rotate independently using the ESP32. He managed to make the motors rotate for a short period of time, because we encountered the same issue as before: the insufficiency of two batteries to power all four DC motors and the ESP32 for a longer period of time.  Consequently, the batteries needed frequent recharging. However, the code appears to be functioning as intended despite this setback.

Important notes

We made use of the identical code as previously, but with a modification in the wiring configuration. This involved linking the pins of the modules to the corresponding pins on the ESP32, due to the dissimilar pin layouts between the Arduino Nano and ESP32.

Pictures: (no good pictures were taken)

-   Two L298N modules connected to the ESP32.

![](https://lh5.googleusercontent.com/jCgT_PuAkkfiMstmRjTqQQvZzkCjojyAQwzF2lEgf0g6x1C05uke2cN2Sd23m0vzPd1uaLd6pDf1y_KxvWweqDvo-6KBDdhnp7Z0KVODOLQDPEgk0aPTA5TJfnJ190j-Xt361pi0VfGeymPTxCPnqj4)

Algorithm:

#include <analogWrite.h>

#include <ESP32PWM.h>

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 26;

int motor2in3 = 27;          

int motor2in4 = 25;

int motor3enA = 18;

int motor3in1 = 17;

int motor3in2 = 5;

int motor4enB = 4; 

int motor4in3 = 16;

int motor4in4 = 15;

int state;

int motorSpeed = 170;

void setup()

{

  Serial.begin(115200);

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

}

/**************************************************************/

void loop()

{

  if (Serial.available() > 0){

    state = Serial.read();

    if (state == 'F'){

      Serial.println("Go North");

      forward();

    } else if (state == 'B'){

      Serial.println("Go South");

      backward();

    } else if (state == 'L'){

      Serial.println("Go West");

      left();

    } else if (state == 'R'){

      Serial.println("Go East");

      right();

    } else if (state == 'N'){

      Serial.println("Go NorthWest");

      NorthWest();

    } else if (state == 'n'){

      Serial.println("Go NorthEast");

      NorthEast();

    } else if (state == 'Z'){

      Serial.println("Go SouthWest");

      SouthWest();

    } else if (state == 'z'){

      Serial.println("Go SouthEast");

      SouthEast();

    } else if (state == 'C'){

      Serial.println("Rotating CCW");

      rotateCCW();

    } else if (state == 'c'){

      Serial.println("Rotating CW");

      rotateCW();

    } else if (state == 'S'){

      Serial.println("Stop");

      stop();

    }

  }

}

/**************************************************************/

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stop() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

Day 11  (29/05/2022)

Seeing that our batteries constantly had to be charged, our programmer tried to make an unlimited power supply, only for testing purposes, until the wheels rotate as they're supposed to, so that we did not have to charge or make use of any batteries. At the end of our project we'll use batteries again, when we'll know that our code works perfectly.  So our programmer tried to use a pc charger as a power supply (input:100-240V and output:19V) and he connected it to both of the L298N modules and the ESP32. At first it worked fine, but too much power was going into the L298N modules and the ESP32, and because of this, our ESP32 and a DC motor burned.

Day 12  (01/06/2022)

Our programmer went to the lab to get a new ESP32 and a dc motor, because he had burned the previous ones. Mr. Theo also advised us that we could try to automate our project, with the use of 3 ultrasonic sensors. This time he attempted to create an alternate, unlimited power supply with a lower voltage output than that of a PC charger. To achieve this, he used two phone chargers with input ratings of 100-240V and output of 7V each, connecting them to both L298N modules and the ESP32. This time everything went well, the output of the voltage was enough to power the entire project. As a result, we don't have to use any batteries or wait for the batteries to charge to start testing our project again. Now when we started testing our project again, we saw that the motors could move in the desired directions, indicating that our code is functioning correctly (we used the same algorithm as the previous one written in day 10).

Pictures:

-   The chargers we used as an unlimited power supply.

![](https://lh5.googleusercontent.com/7S1Z5o96QvWwbuljSv1R7_TRbTpbGX91Hh9_eOvahz8BrQ9JkwW83u3ZaLKP6guERW-f6-bbBrlM7tl-5gs4GZHEFLQ4HLo8bbnsPZjpz2OfghHNe6bCZZwT3UKBK-_nFZZc15bB5P_BLbxql-n79cA)

Day 13  (04/06/2022)

To secure the components in our project and prevent any movement while it's in motion, our team created holes in the lasered part and used tie-wraps to fasten them to the body of our project.

Pictures:

-   Components tie-wrapped to the body of our project to prevent them from moving.

![](https://lh3.googleusercontent.com/i9OPtLKgZvTZttRZd8aQcHTKF8DM45Luyt-o8IF-DIpcOXtBeY0ro8iNKJkCrK3O25c1MgWMXXVGlW0UidDpzr60pGp7EwIhUwFuNFLRcPKXcXEpsoUx_-HEyVXd0jnQ6sGSXkntJUYWJE_QiCCBix4)

Day 14 (07/06/2023)

Mr. Theo recommended automating our project using three ultrasonic sensors. Initially, we attempted to use as few pins as possible, but it proved to be challenging. We first attempted to link the echo pins of the three ultrasonic sensors to different pins on the ESP32 and the trigger pins to the same pin on the ESP32, but this configuration was unsuccessful. We attempted to reverse the setup, but that also didn't work. Finally, we connected the echo and trigger pins of each ultrasonic sensor to different pins, and this setup worked perfectly. Our team members recommended that we also place a servo motor to adjust the leaning of the seat for the comfort of potential buyers, so we also decided to do that.

Important notes

We decided that we'll try to automate our project in the end if we had enough time left, as seen that that is one of the most challenging and difficult feature.

Pictures:

-   Our rover with ultrasonic sensors and a servo motor.

![](https://lh4.googleusercontent.com/YxvDcFgtCOiNFJFHRuSmv4hltT51gP5NM3pdhSst8Xvell2Est6v41m7XoKq2BKdUFiLYCr1AY0g58AasCKEnfQzrY-iap5BL6Ze6Nsg8BhNpyuDNKw5hDAWLoxLMeqkwnJuq-fIujSIsDBRGW3zUGM)

Algorithm:

#include <ESP32Servo.h>

#include <analogWrite.h>

#include <ESP32PWM.h>

Servo myServo;

int servoPin = 19;

/******************************************************/

int trig_F = 22;

double echo_F = 21;

double duration_F;

double distance_F;

int trig_R = 32;

double echo_R = 35;

double duration_R;

double distance_R;

int trig_L = 33;

double echo_L = 34;

double duration_L;

double distance_L;

/******************************************************/

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 26;

int motor2in3 = 27;          

int motor2in4 = 25;

int motor3enA = 18;

int motor3in1 = 17;

int motor3in2 = 5;

int motor4enB = 4; 

int motor4in3 = 16;

int motor4in4 = 15;

int state;

int motorSpeed = 170;

void setup()

{

  Serial.begin(115200);

  /******************************************************/

  myServo.setPeriodHertz(50); 

  myServo.attach(servoPin);

  /******************************************************/

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

  /******************************************************/

  pinMode(trig_F,OUTPUT);

  pinMode(trig_L,OUTPUT);

  pinMode(trig_R,OUTPUT);

  pinMode(echo_F,INPUT);

  pinMode(echo_L,INPUT);

  pinMode(echo_R,INPUT);

}

/**************************************************************/

void loop()

{

  if (Serial.available() > 0){

    state = Serial.read();

    if (state == 'F'){

      Serial.println("Go North");

      forward();

      Serial.print(motorSpeed);

    } else if (state == 'B'){

      Serial.println("Go South");

      backward();

    } else if (state == 'L'){

      Serial.println("Go West");

      left();

    } else if (state == 'R'){

      Serial.println("Go East");

      right();

    } else if (state == 'N'){

      Serial.println("Go NorthWest");

      NorthWest();

    } else if (state == 'n'){

      Serial.println("Go NorthEast");

      NorthEast();

    } else if (state == 'Z'){

      Serial.println("Go SouthWest");

      SouthWest();

    } else if (state == 'z'){

      Serial.println("Go SouthEast");

      SouthEast();

    } else if (state == 'C'){

      Serial.println("Rotating CCW");

      rotateCCW();

    } else if (state == 'c'){

      Serial.println("Rotating CW");

      rotateCW();

    } else if (state == 'S'){

      Serial.println("Stop");

      stop();

    } else if (state = Serial.parseInt()){

      int angle = state;

      myServo.write(angle);

      Serial.println("Received angle: " + String(angle));

    }

  }

 ultra_F();

 ultra_L();

 ultra_R();

 Serial.println("");

 delay(1000);

 }

/**************************************************************/

/*                                                                  Motors                                                            */

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stop() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

/*                                                                  Ultrasonic sensors                                                           */

void ultra_F()

{

  digitalWrite(trig_F,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_F,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_F,LOW);

  duration_F = pulseIn(echo_F,HIGH);

  distance_F = duration_F*0.0343/2;

  Serial.print("Forward distance: ");

  Serial.print(distance_F);

  Serial.print(" cm, ");

}

void ultra_L()

{

  digitalWrite(trig_L,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_L,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_L,LOW);

  duration_L = pulseIn(echo_L,HIGH);

  distance_L = duration_L*0.0343/2;

  Serial.print("Left distance: ");

  Serial.print(distance_L);

  Serial.print(" cm, ");

}

void ultra_R()

{

  digitalWrite(trig_R,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_R,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_R,LOW);

  duration_R = pulseIn(echo_R,HIGH);

  distance_R = duration_R*0.0343/2;

  Serial.print("Right distance:: ");

  Serial.print(distance_R);

  Serial.print(" cm");

}

Day 15 (10/06/2023)

We were deciding whether our project would be controlled via bluetooth or via wifi. We found out that the ADC2 pins on the ESP32 cannot be used when the ESP32 module is connected to Wi-Fi and because of that we decided to control our rover via bluetooth. And if we wanted to control our rover via wifi it would be very challenging to control the motors, because we need 12 different pins to control 4 motors independently.

Important notes

When controlling our rover via bluetooth, we experienced difficulties controlling the servo motor through Bluetooth. The Bluetooth connection got disconnected most of the time when we tried to control the servo motor.

Pictures:

-   Pinout of the ESP32

![](https://lh4.googleusercontent.com/4adiELeWckuzfbK58lDA38aYk16APNTO_6qz2HaZSP6He1i7N891b3rLYVYNqi-mYVjO7QSDeBudDkt8qctxJgVwBwQN9EwTe-CKsNEF194LGXv-OWs1qG18iK7_jdPXVACC8AOYBssAKGM-F1AuyiI)

Algorithm:

#include <ESP32Servo.h>

#include <analogWrite.h>

#include <ESP32PWM.h>

#include <SoftwareSerial.h>

#define RX_PIN 16

#define TX_PIN 17

SoftwareSerial BTSerial(RX_PIN, TX_PIN);

Servo myServo;  // create servo object to control a servo

int servoPin = 19;

/******************************************************/

int trig_F = 22;

double echo_F = 21;

double duration_F;

double distance_F;

int trig_R = 32;

double echo_R = 35;

double duration_R;

double distance_R;

int trig_L = 33;

double echo_L = 34;

double duration_L;

double distance_L;

/******************************************************/

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 26;

int motor2in3 = 27;          

int motor2in4 = 25;

int motor3enA = 18;

int motor3in1 = 17; 

int motor3in2 = 5;

int motor4enB = 4; 

int motor4in3 = 16;

int motor4in4 = 15;

int state;

int motorSpeed = 170;

void setup()

{

  Serial.begin(115200);

  BTSerial.begin(9600);

  /******************************************************/

  myServo.setPeriodHertz(50); 

  myServo.attach(servoPin);

  /******************************************************/

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

  /******************************************************/

  pinMode(trig_F,OUTPUT);

  pinMode(trig_L,OUTPUT);

  pinMode(trig_R,OUTPUT);

  pinMode(echo_F,INPUT);

  pinMode(echo_L,INPUT);

  pinMode(echo_R,INPUT);

}

/**************************************************************/

void loop()

{

  if (BTSerial.available() > 0){

    state = BTSerial.read();

    if (state == 'F'){

      Serial.println("Go North");

      forward();

      Serial.print(motorSpeed);

    } else if (state == 'B'){

      Serial.println("Go South");

      backward();

    } else if (state == 'L'){

      Serial.println("Go West");

      left();

    } else if (state == 'R'){

      Serial.println("Go East");

      right();

    } else if (state == 'N'){

      Serial.println("Go NorthWest");

      NorthWest();

    } else if (state == 'n'){

      Serial.println("Go NorthEast");

      NorthEast();

    } else if (state == 'Z'){

      Serial.println("Go SouthWest");

      SouthWest();

    } else if (state == 'z'){

      Serial.println("Go SouthEast");

      SouthEast();

    } else if (state == 'C'){

      Serial.println("Rotating CCW");

      rotateCCW();

    } else if (state == 'c'){

      Serial.println("Rotating CW");

      rotateCW();

    } else if (state == 'S'){

      Serial.println("Stop");

      stop();

    } else if (state = BTSerial.parseInt()){

      int angle = state;

      myServo.write(angle);

      Serial.println("Received angle: " + String(angle));

  }

  //ultra_F();

  //ultra_L();

  //ultra_R();

  //Serial.println("");

  //delay(1000);

}

/**************************************************************/

/*                                                                  Motors                                                            */

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stop() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

/*                                                                  Ultrasonic sensors                                                           */

void ultra_F()

{

  digitalWrite(trig_F,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_F,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_F,LOW);

  duration_F = pulseIn(echo_F,HIGH);

  distance_F = duration_F*0.0343/2;

  Serial.print("Forward distance: ");

  Serial.print(distance_F);

  Serial.print(" cm, ");

}

void ultra_L()

{

  digitalWrite(trig_L,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_L,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_L,LOW);

  duration_L = pulseIn(echo_L,HIGH);

  distance_L = duration_L*0.0343/2;

  Serial.print("Left distance: ");

  Serial.print(distance_L);

  Serial.print(" cm, ");

}

void ultra_R()

{

  digitalWrite(trig_R,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_R,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_R,LOW);

  duration_R = pulseIn(echo_R,HIGH);

  distance_R = duration_R*0.0343/2;

  Serial.print("Right distance:: ");

  Serial.print(distance_R);

  Serial.print(" cm");

}

Day 16 (11/06/2023)

Because the bluetooth constantly got disconnected when controlling the servo motor, we decided to place a potentio meter so that the leaning (controlled by the servo motor) could easily be adjusted by the potential buyer while sitting in the wheelchair. So we connected the potentio meter to our ESP32 and tried to control the servo motor and it worked. The bluetooth also stopped disconnecting.

Important notes

One of our teammates made a seat for our rover, which you can see in the picture.

Pictures:

Our rover now has a potentio meter to control the leaning of the seat with a servo motor.

![](https://lh3.googleusercontent.com/-_AzByoQ-6p4YJ_RIT2GgNy4Ws4or-AfwxQ-zorF79DY3DfmSBYtqdYOcYO-8c0VNEnSD80FZzL82LkvoGXNakLCjW8KVwPJGBjZWPG6hTrTux7rb5H2ZOJHyos6YuhXxt6MO3hfuUizyqLH-MakRgs)

Algorithm:

#include <ESP32Servo.h>

#include <analogWrite.h>

#include <ESP32PWM.h>

#include <SoftwareSerial.h>

#define RX_PIN 16

#define TX_PIN 17

SoftwareSerial BTSerial(RX_PIN, TX_PIN);

Servo myServo;  // create servo object to control a servo

int servoPin = 19;

/******************************************************/

int trig_F = 22;

double echo_F = 21;

double duration_F;

double distance_F;

int trig_R = 32;

double echo_R = 35;

double duration_R;

double distance_R;

int trig_L = 33;

double echo_L = 34;

double duration_L;

double distance_L;

/******************************************************/

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 26;

int motor2in3 = 27;          

int motor2in4 = 25;

int motor3enA = 18;

int motor3in1 = 17; 

int motor3in2 = 5;

int motor4enB = 4; 

int motor4in3 = 16;

int motor4in4 = 15;

int state;

int motorSpeed = 170;

void setup()

{

  Serial.begin(115200);

  BTSerial.begin(9600);

  /******************************************************/

  myServo.setPeriodHertz(50); 

  myServo.attach(servoPin);

  /******************************************************/

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

  /******************************************************/

  pinMode(trig_F,OUTPUT);

  pinMode(trig_L,OUTPUT);

  pinMode(trig_R,OUTPUT);

  pinMode(echo_F,INPUT);

  pinMode(echo_L,INPUT);

  pinMode(echo_R,INPUT);

}

/**************************************************************/

void loop()

{

Int pot_value = analogRead(pot);

  int leaning = map(pot_value, 0,4095,0,90);

  myServo.write(leaning);

  if (BTSerial.available() > 0){

    state = BTSerial.read();

    if (state == 'F'){

      Serial.println("Go North");

      forward();

      Serial.print(motorSpeed);

    } else if (state == 'B'){

      Serial.println("Go South");

      backward();

    } else if (state == 'L'){

      Serial.println("Go West");

      left();

    } else if (state == 'R'){

      Serial.println("Go East");

      right();

    } else if (state == 'N'){

      Serial.println("Go NorthWest");

      NorthWest();

    } else if (state == 'n'){

      Serial.println("Go NorthEast");

      NorthEast();

    } else if (state == 'Z'){

      Serial.println("Go SouthWest");

      SouthWest();

    } else if (state == 'z'){

      Serial.println("Go SouthEast");

      SouthEast();

    } else if (state == 'C'){

      Serial.println("Rotating CCW");

      rotateCCW();

    } else if (state == 'c'){

      Serial.println("Rotating CW");

      rotateCW();

    } else if (state == 'S'){

      Serial.println("Stop");

      stop();

    } else if (state = BTSerial.parseInt()){

      int angle = state;

      myServo.write(angle);

      Serial.println("Received angle: " + String(angle));

  }

  //ultra_F();

  //ultra_L();

  //ultra_R();

  //Serial.println("");

  //delay(1000);

}

/**************************************************************/

/*                                                                  Motors                                                            */

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stop() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

/*                                                                  Ultrasonic sensors                                                           */

void ultra_F()

{

  digitalWrite(trig_F,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_F,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_F,LOW);

  duration_F = pulseIn(echo_F,HIGH);

  distance_F = duration_F*0.0343/2;

  Serial.print("Forward distance: ");

  Serial.print(distance_F);

  Serial.print(" cm, ");

}

void ultra_L()

{

  digitalWrite(trig_L,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_L,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_L,LOW);

  duration_L = pulseIn(echo_L,HIGH);

  distance_L = duration_L*0.0343/2;

  Serial.print("Left distance: ");

  Serial.print(distance_L);

  Serial.print(" cm, ");

}

void ultra_R()

{

  digitalWrite(trig_R,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_R,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_R,LOW);

  duration_R = pulseIn(echo_R,HIGH);

  distance_R = duration_R*0.0343/2;

  Serial.print("Right distance:: ");

  Serial.print(distance_R);

  Serial.print(" cm");

}

Day 17 (12/06/2023)

Today we decided to add another feature to our project, the feature is that the potential buyer could also control the speed of our project. So we programmed our code in such a way, so that the buyer could increase or decrease the speed of the rover even when it's being driven manually. And after doing that we came across such a problem that took us days to figure out. Most of the time when we controlled our rover via bluetooth the rover moved smoothly without any problem, the speed of our rover could be increased and decreased, but every time we increased our rover to max speed the bluetooth kept getting disconnected. We tried programming our rover in many different ways but the problem could not be solved.

Algorithm:

#include <ESP32Servo.h>

#include <analogWrite.h>

#include <ESP32PWM.h>

#include <SoftwareSerial.h>

#define RX_PIN 16

#define TX_PIN 17

SoftwareSerial BTSerial(RX_PIN, TX_PIN);

Servo myServo;  // create servo object to control a servo

int servoPin = 19;

/******************************************************/

int trig_F = 22;

double echo_F = 21;

double duration_F;

double distance_F;

int trig_R = 32;

double echo_R = 35;

double duration_R;

double distance_R;

int trig_L = 33;

double echo_L = 34;

double duration_L;

double distance_L;

/******************************************************/

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 26;

int motor2in3 = 27;          

int motor2in4 = 25;

int motor3enA = 18;

int motor3in1 = 23; //17

int motor3in2 = 5;

int motor4enB = 4; 

int motor4in3 = 3; //16

int motor4in4 = 15;

int state;

int leaning;

int pot = 2;

int motorSpeed = 255;

void setup()

{

  Serial.begin(115200);

  BTSerial.begin(9600);

  /******************************************************/

  myServo.setPeriodHertz(50); 

  myServo.attach(servoPin);

  /******************************************************/

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

  /******************************************************/

  pinMode(trig_F,OUTPUT);

  pinMode(trig_L,OUTPUT);

  pinMode(trig_R,OUTPUT);

  pinMode(echo_F,INPUT);

  pinMode(echo_L,INPUT);

  pinMode(echo_R,INPUT);

}

/**************************************************************/

void loop()

{

  int pot_value = analogRead(pot);

  Serial.println(pot_value);

  int leaning = map(pot_value, 0,4095,0,90);

  myServo.write(leaning);

  /*int pot_value = analogRead(pot);

  //Serial.println(pot_value);

  int motorSpeed = map(pot_value, 0,4095,0,255);

  //myServo.write(leaning);

  analogWrite(motor1enA, motorSpeed);

  analogWrite(motor2enB, motorSpeed);

  analogWrite(motor3enA, motorSpeed);

  analogWrite(motor4enB, motorSpeed); */

  if (BTSerial.available() > 0){

    state = BTSerial.read();

    if (state == '+'){

      motorSpeed = motorSpeed + 10;

      Serial.print("motorSpeed up: ");

      Serial.println(motorSpeed);

      if (motorSpeed > 255) {

        motorSpeed = 255;

      }      

      analogWrite(motor1enA, motorSpeed);

      analogWrite(motor2enB, motorSpeed);

      analogWrite(motor3enA, motorSpeed);

      analogWrite(motor4enB, motorSpeed);

    } else if (state == '-'){

        motorSpeed = motorSpeed - 10;

        Serial.print("motorSpeed down: ");

        Serial.println(motorSpeed);

        if (motorSpeed <= 140) {

          motorSpeed = 140;

        }

        analogWrite(motor1enA, motorSpeed);

        analogWrite(motor2enB, motorSpeed);

        analogWrite(motor3enA, motorSpeed);

        analogWrite(motor4enB, motorSpeed);

    } else if (state == 'F'){

      Serial.println("Go North");

      forward();

      Serial.println(motorSpeed);

    } else if (state == 'B'){

      Serial.println("Go South");

      backward();

    } else if (state == 'L'){

      Serial.println("Go West");

      left();

    } else if (state == 'R'){

      Serial.println("Go East");

      right();

    } else if (state == 'N'){

      Serial.println("Go NorthWest");

      NorthWest();

    } else if (state == 'n'){

      Serial.println("Go NorthEast");

      NorthEast();

    } else if (state == 'Z'){

      Serial.println("Go SouthWest");

      SouthWest();

    } else if (state == 'z'){

      Serial.println("Go SouthEast");

      SouthEast();

    } else if (state == 'C'){

      Serial.println("Rotating CCW");

      rotateCCW();

    } else if (state == 'c'){

      Serial.println("Rotating CW");

      rotateCW();

    } else if (state == 'S'){

      Serial.println("Stop");

      stopm();

    }

  }

  //ultra_F();

  //ultra_L();

  //ultra_R();

  //Serial.println("");

  //delay(1000);

  //myServo.write(0);

  //Serial.println("0");

  //delay(10000);

  //myServo.write(45);

  //Serial.println("45");

  //delay(10000);

  //myServo.write(90);

  //Serial.println("90");

  //delay(10000);

}

/**************************************************************/

/*                                                                  Motors                                                            */

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stopm() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

/*                                                                  Ultrasonic sensors                                                           */

void ultra_F()

{

  digitalWrite(trig_F,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_F,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_F,LOW);

  duration_F = pulseIn(echo_F,HIGH);

  distance_F = duration_F*0.0343/2;

//  Serial.print("Forward distance: ");

//  Serial.print(distance_F);

//  Serial.print(" cm, ");

}

void ultra_L()

{

  digitalWrite(trig_L,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_L,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_L,LOW);

  duration_L = pulseIn(echo_L,HIGH);

  distance_L = duration_L*0.0343/2;

//  Serial.print("Left distance: ");

//  Serial.print(distance_L);

//  Serial.print(" cm, ");

}

void ultra_R()

{

  digitalWrite(trig_R,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_R,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_R,LOW);

  duration_R = pulseIn(echo_R,HIGH);

  distance_R = duration_R*0.0343/2;

//  Serial.print("Right distance:: ");

//  Serial.print(distance_R);

//  Serial.print(" cm");

}

Day 17 (12/06/2023)

We thought that there was a problem with the bluetooth module, so we decided to use the integrated bluetooth of the ESP32 itself. Before we did that, we took out every wire connected to the ESP32, because we're not using a bluetooth module anymore, so we could now use 2 more pins of the ESP32. We wanted to connect the wires in such a way to the ESP32 so that the insides of our rover would not be messy and so that not too much pressure would be applied to the wires when we closed the top of our rover. Even after using the integrated bluetooth of the ESP32 we still had the same problem. When we drove our rover at top speed, the bluetooth kept getting disconnected.

Algorithm:

#include <ESP32Servo.h>  

#include "BluetoothSerial.h"

#if !defined(CONFIG_BT_ENABLED) || !defined(CONFIG_BLUEDROID_ENABLED)

#error Bluetooth is not enabled! Please run `make menuconfig` to and enable it

#endif

char receivedChar;// received value will be stored as CHAR in this variable

BluetoothSerial SerialBT;

Servo myServo;  // create servo object to control a servo

int servoPin = 18;

int leaning;

int pot = 36;

int motorSpeed = 140;

/******************************************************/

int trig_F = 22;

double echo_F = 21;

double duration_F;

double front_distance;

int trig_R = 32;

double echo_R = 35;

double duration_R;

double right_distance;

int trig_L = 33;

double echo_L = 34;

double duration_L;

double left_distance;

/******************************************************/

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 25; 

int motor2in3 = 27;          

int motor2in4 = 26;

int motor3enA = 5; 

int motor3in1 = 17; 

int motor3in2 = 16;

int motor4enB = 15; /

int motor4in3 = 4;  

int motor4in4 = 2;

void setup(){

  Serial.begin(115200);

  SerialBT.begin("LeftOvers-ESP32"); //Bluetooth device name

  Serial.println("The device started, now you can pair it with bluetooth!");

  //BTSerial.begin(9600);

  /******************************************************/

  myServo.setPeriodHertz(50); 

  myServo.attach(servoPin);

  /******************************************************/

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

  /******************************************************/

  pinMode(trig_F,OUTPUT);

  pinMode(trig_L,OUTPUT);

  pinMode(trig_R,OUTPUT);

  pinMode(echo_F,INPUT);

  pinMode(echo_L,INPUT);

  pinMode(echo_R,INPUT);

}

/**************************************************************/

void loop(){

  int pot_value = analogRead(pot);

  int leaning = map(pot_value, 0,4095,0,90);

  myServo.write(leaning);

  if (Serial.available()) {

    SerialBT.write(Serial.read());

  }

  if (SerialBT.available()) {

    Serial.write(SerialBT.read());  

  }

  delay(20);

  receivedChar =(char)SerialBT.read();

  if (receivedChar == '+'){

    motorSpeed = motorSpeed + 10;

    if (motorSpeed > 255) {

      motorSpeed = 255;

    }      

    SerialBT.print("Speed increased to: ");

    SerialBT.print(motorSpeed);

    Serial.print("Speed increased to: ");

    Serial.println(motorSpeed);

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

  } 

  else if (receivedChar == '-'){    

    motorSpeed = motorSpeed - 10;

    if (motorSpeed <= 100) {

      motorSpeed = 100;

    }

    SerialBT.print("Speed decreased to: ");

    SerialBT.print(motorSpeed);

    Serial.print("Speed decreased to: ");

    Serial.println(motorSpeed);

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

  } 

  else if (receivedChar == 'y'){

    motorSpeed = 140;

    SerialBT.print("Speed neutralized to: ");

    SerialBT.print(motorSpeed);

    Serial.print("Speed neutralized to: ");

    Serial.println(motorSpeed);

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

  } 

  else if (receivedChar == 'F'){

    SerialBT.print("Go North");

    Serial.println("Go North");

    forward();

    Serial.println(motorSpeed);

  } 

  else if (receivedChar == 'B'){

    SerialBT.print("Go South");

    Serial.println("Go South");

    backward();

  } 

  else if (receivedChar == 'L'){

    SerialBT.print("Go West");

    Serial.println("Go West");

    left();

  } 

  else if (receivedChar == 'R'){

    SerialBT.print("Go East");

    Serial.println("Go East");

    right();

  } 

  else if (receivedChar == 'N'){

    SerialBT.print("Go NorthWest");

    Serial.println("Go NorthWest");

    NorthWest();

  } 

  else if (receivedChar == 'n'){

    SerialBT.print("Go NorthEast");

    Serial.println("Go NorthEast");

    NorthEast();

  } 

  else if (receivedChar == 'Z'){

    SerialBT.print("Go SouthWest");

    Serial.println("Go SouthWest");

    SouthWest();

  } 

  else if (receivedChar == 'z'){

    SerialBT.print("Go SouthEast");

    Serial.println("Go SouthEast");

    SouthEast();

  } 

  else if (receivedChar == 'C'){

    SerialBT.print("Rotating CCW");

    Serial.println("Rotating CCW");

    rotateCCW();

  } 

  else if (receivedChar == 'c'){

    SerialBT.print("Rotating CW");

    Serial.println("Rotating CW");

    rotateCW();

  } 

  else if (receivedChar == 'S'){

    SerialBT.print("Stop");

    Serial.println("Stop");

    stopMotor();

  } 

}

 /**************************************************************/

/*                                                                  Motors                                                            */

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stopMotor() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

/*                                                                  Ultrasonic sensors                                                          */

void ultra_F()

{

  digitalWrite(trig_F,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_F,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_F,LOW);

  duration_F = pulseIn(echo_F,HIGH);

  front_distance = duration_F*0.0343/2;

//  Serial.print("Forward distance: ");

//  Serial.print(front_distance);

//  Serial.print(" cm, ");

}

void ultra_L()

{

  digitalWrite(trig_L,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_L,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_L,LOW);

  duration_L = pulseIn(echo_L,HIGH);

  left_distance = duration_L*0.0343/2;

//  Serial.print("Left distance: ");

//  Serial.print(left_distance);

//  Serial.print(" cm, ");

}

void ultra_R()

{

  digitalWrite(trig_R,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_R,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_R,LOW);

  duration_R = pulseIn(echo_R,HIGH);

  right_distance = duration_R*0.0343/2;

//  Serial.print("Right distance:: ");

//  Serial.print(right_distance);

//  Serial.print(" cm");

}

Day 17 (12/06/2023)

Because the bluetooth kept getting disconnected when the rover was driven at full speed. It seemed as if the rover wasn't getting enough power, even though the rover had a power supply of 12V. So we decided to control our project with bluetooth while the ESP32 was still connected to the laptop, because the laptop can also be seen as a power supply of 5V. And when we made our rover drive at full speed, the bluetooth was still connected to the phone. And now the rover had enough power to maintain the bluetooth connection even when driven at full speed.

Important notes

Right now we're providing the rover, power supplies through 2 chargers and a laptop, but in the hackomation competition we won't be able to do this, so we'll probably need 6 batteries to make our rover drive smoothly and maintain the bluetooth connection.

Day 18 (14/06/2023)

We got batteries from the lab and made our rover drive at full speed and the bluetooth connection was definitely maintained.

Day 19 (16/06/2023)

After successfully enabling their project to move in 8 different directions, rotate clockwise and counterclockwise, adjust leaning, and vary speed, the team's programmer decided to take things to the next level. Our programmer decided to explore the possibility of automating the project. This meant creating a system that would enable the rover to move autonomously, detect obstacles in its path, and take evasive action by turning in a different direction. This would allow the project to navigate its environment without requiring constant human input, making it more efficient and versatile. And the team's programmer was able to do this in almost 9 hours of constant hard work.

Algorithm:

#include <ESP32Servo.h>

#include "BluetoothSerial.h"

#if !defined(CONFIG_BT_ENABLED) || !defined(CONFIG_BLUEDROID_ENABLED)

#error Bluetooth is not enabled! Please run `make menuconfig` to and enable it

#endif

char receivedChar;// received value will be stored as CHAR in this variable

BluetoothSerial SerialBT;

int threshold = 50;

/*

#include <analogWrite.h>

#include <ESP32PWM.h>

#include <SoftwareSerial.h>

#define RX_PIN 

#define TX_PIN

SoftwareSerial BTSerial(RX_PIN, TX_PIN);*/

Servo myServo;  // create servo object to control a servo

int servoPin = 18;

int leaning;

int pot = 36;

int motorSpeed = 140;

/******************************************************/

int trig_F = 22;

double echo_F = 21;

double duration_F;

double front_distance;

int trig_R = 32;

double echo_R = 35;

double duration_R;

double right_distance;

int trig_L = 33;

double echo_L = 34;

double duration_L;

double left_distance;

/******************************************************/

int motor1enA = 13;

int motor1in1 = 12;

int motor1in2 = 14;

int motor2enB = 25; //26  13juni

int motor2in3 = 27;          

int motor2in4 = 26; //25  13juni

int motor3enA = 5;  //18; 13-6

int motor3in1 = 17; //23; 13-6

int motor3in2 = 16; //5;  13-6

int motor4enB = 15; //4;       13-6

int motor4in3 = 4;  //3; //16  13-6   pin 3 speelt echt grote rol bij boot

int motor4in4 = 2;  //15;      13-6

void setup(){

  Serial.begin(115200);

  SerialBT.begin("LeftOvers-ESP32"); //Bluetooth device name

  Serial.println("The device started, now you can pair it with bluetooth!");

  //BTSerial.begin(9600);

  /******************************************************/

  myServo.setPeriodHertz(50); 

  myServo.attach(servoPin);

  /******************************************************/

  pinMode(motor1enA, OUTPUT);

  pinMode(motor1in1, OUTPUT);

  pinMode(motor1in2, OUTPUT);

  analogWrite(motor1enA, motorSpeed);

  pinMode(motor2enB, OUTPUT);

  pinMode(motor2in3, OUTPUT);

  pinMode(motor2in4, OUTPUT);

  analogWrite(motor2enB, motorSpeed);

  pinMode(motor3enA, OUTPUT);

  pinMode(motor3in1, OUTPUT);

  pinMode(motor3in2, OUTPUT);

  analogWrite(motor3enA, motorSpeed);

  pinMode(motor4enB, OUTPUT);

  pinMode(motor4in3, OUTPUT);

  pinMode(motor4in4, OUTPUT);

  analogWrite(motor4enB, motorSpeed);

  /******************************************************/

  pinMode(trig_F,OUTPUT);

  pinMode(trig_L,OUTPUT);

  pinMode(trig_R,OUTPUT);

  pinMode(echo_F,INPUT);

  pinMode(echo_L,INPUT);

  pinMode(echo_R,INPUT);

}

/**************************************************************/

void loop(){

  int pot_value = analogRead(pot);

  int leaning = map(pot_value, 0,4095,0,90);

  myServo.write(leaning);

  if (Serial.available()) {

    SerialBT.write(Serial.read());

  }

  if (SerialBT.available()) {

    Serial.write(SerialBT.read());  

  }

  delay(20);

  receivedChar =(char)SerialBT.read();

  if (receivedChar == '+'){

    motorSpeed = motorSpeed + 10;

    if (motorSpeed > 255) {

      motorSpeed = 255;

    }      

    SerialBT.print("Speed increased to: ");

    SerialBT.print(motorSpeed);

    Serial.print("Speed increased to: ");

    Serial.println(motorSpeed);

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

  } 

  else if (receivedChar == '-'){    

    motorSpeed = motorSpeed - 10;

    if (motorSpeed <= 100) {

      motorSpeed = 100;

    }

    SerialBT.print("Speed decreased to: ");

    SerialBT.print(motorSpeed);

    Serial.print("Speed decreased to: ");

    Serial.println(motorSpeed);

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

  } 

  else if (receivedChar == 'y'){

    motorSpeed = 140;

    SerialBT.print("Speed neutralized to: ");

    SerialBT.print(motorSpeed);

    Serial.print("Speed neutralized to: ");

    Serial.println(motorSpeed);

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

  } 

  else if (receivedChar == 'F'){

    SerialBT.print("Go North");

    Serial.println("Go North");

    forward();

    Serial.println(motorSpeed);

  } 

  else if (receivedChar == 'B'){

    SerialBT.print("Go South");

    Serial.println("Go South");

    backward();

  } 

  else if (receivedChar == 'L'){

    SerialBT.print("Go West");

    Serial.println("Go West");

    left();

  } 

  else if (receivedChar == 'R'){

    SerialBT.print("Go East");

    Serial.println("Go East");

    right();

  } 

  else if (receivedChar == 'N'){

    SerialBT.print("Go NorthWest");

    Serial.println("Go NorthWest");

    NorthWest();

  } 

  else if (receivedChar == 'n'){

    SerialBT.print("Go NorthEast");

    Serial.println("Go NorthEast");

    NorthEast();

  } 

  else if (receivedChar == 'Z'){

    SerialBT.print("Go SouthWest");

    Serial.println("Go SouthWest");

    SouthWest();

  } 

  else if (receivedChar == 'z'){

    SerialBT.print("Go SouthEast");

    Serial.println("Go SouthEast");

    SouthEast();

  } 

  else if (receivedChar == 'C'){

    SerialBT.print("Rotating CCW");

    Serial.println("Rotating CCW");

    rotateCCW();

  } 

  else if (receivedChar == 'c'){

    SerialBT.print("Rotating CW");

    Serial.println("Rotating CW");

    rotateCW();

  } 

  else if (receivedChar == 'S'){

    SerialBT.print("Stop");

    Serial.println("Stop");

    stopMotor();

  } 

  else if (receivedChar == 'M'){

    SerialBT.print("Self-Driving Mode: On");

    Serial.println("Self-Driving Mode: On");

    motorSpeed = 100;

    analogWrite(motor1enA, motorSpeed);

    analogWrite(motor2enB, motorSpeed);

    analogWrite(motor3enA, motorSpeed);

    analogWrite(motor4enB, motorSpeed);

        /*************************************************************/

    bool exitloop = false;

    while (!exitloop){

      ultra_F();

      Serial.print("Front distance: ");

      Serial.println(front_distance);

      ultra_R();

      Serial.print("Right distance: ");

      Serial.println(right_distance);

      ultra_L();

      Serial.print("Left distance: ");

      Serial.println(left_distance);

      if (front_distance > threshold) {

        Serial.println("S-DM: Going Forward");

        Serial.println(" ");

        forward();

      } else if (right_distance > threshold * 2) {

        Serial.println("S-DM: Turning right");

        rotateCW();

        delay(3000); 

        Serial.println("S-DM: Going Forward");

        Serial.println(" ");

        forward(); 

      } else if (left_distance > threshold * 2) {

        Serial.println("S-DM: Turning left");

        rotateCCW();

        delay(3000);

        Serial.println("S-DM: Going Forward");

        Serial.println(" ");

        forward();

      } else {

        stopMotor();

        Serial.println("S-DM: Dead end! Turn Around");

        delay(1200);

        Serial.println("S-DM: Turning right");

        rotateCW();

        delay(6000); 

        Serial.println("S-DM: Going Forward");

        Serial.println(" ");

        forward();

      }

      delay(500);

      if (SerialBT.available() > 0){

        receivedChar = (char)SerialBT.read();

        //char receivedChar = Serial.read();

        if (receivedChar = 'm'){

          exitloop = true;

          SerialBT.print("Self-Driving Mode: Off");

          Serial.println("Self-Driving Mode: Off");

          stopMotor();

        }

      }

    }

  }

}

 /**************************************************************/

/*                                                                  Motors                                                            */

void forward() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void backward() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void right() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void left() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void NorthWest() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void NorthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void SouthWest() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void SouthEast() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

void rotateCW() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, HIGH);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, HIGH);

  digitalWrite(motor3in1, HIGH);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, HIGH);

  digitalWrite(motor4in4, LOW);

}

void rotateCCW() 

{

  digitalWrite(motor1in1, HIGH);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, HIGH);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, HIGH);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, HIGH);

}

void stopMotor() 

{

  digitalWrite(motor1in1, LOW);

  digitalWrite(motor1in2, LOW);

  digitalWrite(motor2in3, LOW);

  digitalWrite(motor2in4, LOW);

  digitalWrite(motor3in1, LOW);

  digitalWrite(motor3in2, LOW);

  digitalWrite(motor4in3, LOW);

  digitalWrite(motor4in4, LOW);

}

/*                                                                  Ultrasonic sensors                                                          */

void ultra_F()

{

  digitalWrite(trig_F,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_F,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_F,LOW);

  duration_F = pulseIn(echo_F,HIGH);

  front_distance = duration_F*0.0343/2;

//  Serial.print("Forward distance: ");

//  Serial.print(front_distance);

//  Serial.print(" cm, ");

}

void ultra_L()

{

  digitalWrite(trig_L,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_L,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_L,LOW);

  duration_L = pulseIn(echo_L,HIGH);

  left_distance = duration_L*0.0343/2;

//  Serial.print("Left distance: ");

//  Serial.print(left_distance);

//  Serial.print(" cm, ");

}

void ultra_R()

{

  digitalWrite(trig_R,LOW);

  delayMicroseconds(2);

  digitalWrite(trig_R,HIGH);

  delayMicroseconds(10);

  digitalWrite(trig_R,LOW);

  duration_R = pulseIn(echo_R,HIGH);

  right_distance = duration_R*0.0343/2;

//  Serial.print("Right distance:: ");

//  Serial.print(right_distance);

//  Serial.print(" cm");

}

Day 20 (17/06/2023)

The day of the HackOmation finals had arrived, and the team was ready to showcase their prototype wheelchair. The programmer presented the project to the judges in a clear and professional manner, explaining how it worked and highlighting its capabilities. The judges were impressed with what they saw and heard, and the team's project stood out among the others. After careful consideration, the judges announced that our team had won first place in the competition. The team was thrilled to have their hard work and dedication recognized in this way. Winning the HackOmation finals was a major achievement and a validation of their skills and creativity. The team members were proud of what they had accomplished.

Important notes

Completing this project did not take us only 20 days and certainly was no small task. From initial design to final programming, the entire process took more than a month of hard work and dedication. The team's programmer was particularly committed to making the project the best it could be. He even took the project home with him, spending countless hours refining the design and adding new features. It was not uncommon for him to work through the night, fueled by his passion for the project. Despite the long hours and occasional sleepless nights, the team's efforts paid off in the end. The project was equipped with a wide range of features that exceeded the team's initial expectations, thanks in large part to the programmer's tireless work.

Pictures:

-   The team's programmer.

![](https://lh5.googleusercontent.com/VFwg-HSvPTRAMsAaYQYa0e2fPPUrxmMvTzHV_j8xmKWbyEGOyDKrOG-j9LY8HZK-QrcK5FLpyb8MUBLxWgM2uXQbnkzkt75AHAr3b4sSL-WQ35l0IcSI2fkv-c21enCVLCoM7ZN1zMA9JZW53qT0fFs)

-   Team LeftOvers

![](https://lh4.googleusercontent.com/ludQ8xylmgY8lug4-9DKEwkn2oE4cxoYQrou4Uy1b-Y7avLua-auWXBUcWyZ4qX-nFXhK-C5G_OesUKCABT8aUNUAZLQ8sd81aQJ2tavlsQp_TAd7WQhD0PKnTE79KSGcrxR2tqpFWJ7n4RYEf_64b4)

-   Presentation 

![](https://lh3.googleusercontent.com/DyfcgKfMMK4NJU76Em9tlTrkXPrp-vzxysTEwouNTOL872LMqaSk1NEGiTsp5lIzn4-XAjKMrM2EGVgNQQdYHGP5_kmdMDDQ7gLTn3yLIU998NQ7woY1ASCfJi8HvDgMwR5KLHv-fT89SV4R_Vob6OU)

THE END