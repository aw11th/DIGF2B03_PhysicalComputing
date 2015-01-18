# DIGF2B03_PhysicalComputing

/*
LAB 2- Control one LED blink wih three buttons
Alisa Maria Wronski 
DIGF2B03 PhysicalComputing
OCAD University
Created on Sun Jan 18 2015

Based on:
Fade Example, Free Domain, Arduino program
Example Title, David Cuartielles, http://arduino.cc/en/Tutorial/Blink
Button, Tom Igo and DojoDave , http://www.arduino.cc/en/Tutorial/Button

 Question I have:
Why does the first button just turn it on but not off when not pressed
The second button turns on and fades, when unpressed the LED remains at the last brightness
The third button blinks when pressed, and off when not pressed. 

If LED is on still from the first button, why does the blink button turn it off? */ 



int ledPin = 9; // choose the pin for the LED 
int inputPin1 = 2; // button 1 for just on
int inputPin2 = 3; // button 2 for fading blink
int inputPin3 = 4; // button 3 for fast blink

int brightness = 0;    // how bright the LED is for fade
int fadeAmount = 5;    // how many points to fade the LED by

  
void setup() { 
  pinMode(ledPin, OUTPUT);   // make the LED emit light (output)
  pinMode(inputPin1, INPUT); // button 1 takes in information (input)
  pinMode(inputPin2, INPUT); // button 2 takes in information (input) 
  pinMode(inputPin3, INPUT); // button 3 takes in information (input)

} void loop()

{ 
  if (digitalRead(inputPin1) == LOW) { //if button 1 is pressed
    digitalWrite(ledPin, HIGH);        // then turn the LED on
{
}  
    
  } if (digitalRead(inputPin2) == LOW) {        //if button 2 is pressed
      analogWrite(ledPin, brightness);          // turn on LED to the set brightness
      brightness = brightness + fadeAmount;     //the brightess varies by the fade amount (top row)
      if (brightness == 0 || brightness == 255) { //reverse the direction of fading
      fadeAmount = -fadeAmount ; 
  }     
  delay(10);   // ten milliseconds 
{  
}


 
   } if  (digitalRead(inputPin3) == LOW) {   //when button is pressed
           digitalWrite(ledPin, HIGH);       // turn LED on
           delay(200);                       //for only 200 miliseconds
           digitalWrite(ledPin, LOW);       // then turn off LED
           delay(200);                       //for 200 milliseconds
  
  } 
} 

 
