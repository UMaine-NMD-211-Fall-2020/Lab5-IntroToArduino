# Lab5: Intro To Arduino
This lab introduces arduino.

## Goals & Required Submissions
### Goals
- Understand what is an arduino
- Understand why you might use an arduino
- Download Arduino IDE. Set up Arduino on your computers
- Write LED Blink Code
- Discuss Building a Circuit. Build Circuit. 

### Submissions
Submit your code in a folder labeled `Lab5_FirstName_LastName` on google drive, or make a github folder, fork this README, then pull request to add the link to your file. 

1. Commented Arduino code with a basic blinking pattern, as zip file or Github submission. Should have lab info at to p. 

(  2, 3, 4 in a separte document in the google drive or in the github readme ).  

2. Picture of your setup. Link to a video of your arduino showing the basic blinking pattern - can upload on google photos using your massive ammount of UMaine Storage. 

3. Short explanation of why your circuit works, can include diagram

4. What would you be interested in doing with an Arduino? Write a paragraph, describing either muliple projects of interest or describing one project in depth.

5. Use Arduinio LED to send a Morse Code message. Class or function use recommended. Zip & Google Drive or Github. Make video of it. 

6. **Extra** Add extra leds to your setup, and make something interesting with lots of leds. Document as done above. 

## Resources

### Examples of Arduino & Art
- [Arduino Art](http://arduinoarts.com/2014/05/9-amazing-projects-where-arduino-art-meet/)
- [Artist who uses Arduino: Erin Gee](https://eringee.net/category/portfolio/robotics/)

### Online Intro to Arduino Walk throughs
- [Arduino Workshop for Beginners, by Core Electronics](https://youtu.be/EdXQUEMOfgU)
The first 14 videos go into detail about what we are doing this week. Much of what we do this week will be Arduino specific, but some things will carry over from class. 
- [Channel of Arduino Projects & Information, by NYU ITP](https://vimeo.com/showcase/6565160?page=3)

## Exercises

### Download & Setup

### Blink LED: Arduino's Hello World

## Class Code
### Wednesday
#### Blink LED 
```arduino
int led_pin = 13;

void setup() {
  // put your setup code here, to run once:
  pinMode( led_pin , OUTPUT );  // tell the Arduino which pin we're using (Pin 13)
  Serial.begin(9600);       // start the serial monitor with rate baudrate
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite( led_pin , HIGH );  // LED ON
  Serial.println("LED ON");
  delay( 2000 );               // wait 2seconds
  digitalWrite( led_pin , LOW );   // LED OFF
  Serial.println("LED OFF");
  delay ( 333 );              // wait 1/3 second

}
```
#### Morse Code
I would make dot & dash into functions too ... and space! We ran out of time. Basically, any building block should be a function

##### What my code looked like at the end of lab
```arduino
/* Lab 5 - NMD 211
 * FirstName LastName
 * Date
 * 
 * Morse Code
 * 
 * Write the message, "Hello World!" in Morse Code.
 * - Dots (short length lights) - 2 second
 * - Dashes ( long length lights) -  4 seconds
 * - break between dots and dashes  - 0.25 seconds
 * - break between letters - 0.5 seconds
 * - break between words - 1 second
*/
int longLength = 4000 ; // 4 seconds, dash
int shortLenth = 2000 ; // 2 second, dot

int led_pin = 13;       // pin to use

void setup() {
  // put your setup code here, to run once:

    pinMode( led_pin , OUTPUT );  // tell the Arduino which pin we're using (Pin 13)  
    Serial.begin(9600);       // start the serial monitor with rate baudrate

}

void loop() {
  // put your main code here, to run repeatedly:
  A();
  
}

void A(){
  Serial.println("A");            // Letter
  // Dot
  digitalWrite( led_pin , HIGH );  // LED ON
  delay( 2000 );                   // wait 2seconds
  digitalWrite( led_pin , LOW );   // LED OFF
  
  // Space between dots and dashes
  delay ( 250 );                    // wait 1/4 second
  
  // Dash
  digitalWrite( led_pin , HIGH );  // LED ON
  delay( 4000 );                   // wait 4 seconds
  digitalWrite( led_pin , LOW );   // LED OFF
  
  // Space between letters
  delay ( 500 );                    // wait 1/4 second
}


```
##### What my code would look like with proper formatting, commenting, and substitutions
It would have
- functions `dot()` and `dash()`
- no hardcoded numbers inside delays. Use the appropriate variables. 
- comments before start of new idea
- comment next to functions you think I won't understand right away

### Friday 
#### Blink LED
```arduino
/* Lab 5 - NMD 211
 * FirstName LastName
 * October 9, 2020
 * 
 * Blink LED
 * 
 * To run, upload code
*/
int pinIn = 13;                   // pin powering LED 

int timeLEDOn = 948 ;             // length of time LED On
int timeLEDOff = 4389 ;           // length of time LED Off

void setup() {
  // put your setup code here, to run once:

  pinMode(pinIn, OUTPUT);          // set pin 13 to put out current

}

void loop() {
  // put your main code here, to run repeatedly:

  // Turn LED on
  digitalWrite( pinIn , HIGH ); // write to pin pinIN with full power
  // wait
  delay(timeLEDOn);  //wait 1 second
  // Turn LED off
  digitalWrite( pinIn , LOW ); // write to pin pinIN with full power
  // wait
  delay(timeLEDOff);  //wait 1 second

}
```
#### Morse Code
```arduino
/* Lab 5 - NMD 211
   FirstName LastName
   October 9, 2020

   Morse Code
   - dots : 300 ms
   - dashes: 1200 ms
   - space between dots &/or dashes: 100 ms
   - space between letters: 300 ms
   - space between words: 2000 ms
*/
// global variables
int pinIn = 13;                   // pin powering LED

int dotLength = 300;              // dots length
int dashLength = 1200;            // dash length
int dotDashSpace = 100;           // space between dots and/or dashes
int letterSpace = 300;            // space between letters
int wordSpace = 2000;             // space between words

void setup() {
  // put your setup code here, to run once:

  pinMode( pinIn, OUTPUT); // set pin to current output

}

void loop() {
  // put your main code here, to run repeatedly:

  A(); // Letter A
}

/* HELPER Functions */

void dot() { // make a dot
  // Turn on
  digitalWrite( pinIn , HIGH );     // write to pin pinIn with full power
  // wait
  delay( dotLength );
  // turn off
  digitalWrite( pinIn, LOW );       // write to pin pinIn with no power
}

void dash() { // make a dash
  // Turn on
  digitalWrite( pinIn , HIGH );     // write to pin pinIn with full power
  // wait
  delay( dashLength );
  // turn off
  digitalWrite( pinIn, LOW );       // write to pin pinIn with no power
}

void A() { // make letter A
  dot();
  // wait between dot and dash
  delay( dotDashSpace );

  dash();
  // wait between letters
  delay ( letterSpace );
  }
```
## Submissions
If you plan to submit on github, submit below 
- [Lab5-FirstName-LastName](http://www.example.com)
