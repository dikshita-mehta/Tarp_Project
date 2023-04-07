#include "OakOLED.h"
#include <Adafruit_GFX.h>
#include "Wire.h"

const int flexPin0 = A0; 
const int flexPin1 = A1; 
const int flexPin2 = A2; 
const int flexPin3 = A3; 

const float VCC = 5;			// voltage at Ardunio 5V line
const float R_DIV = 10000.0;	// resistor used to create a voltage divider
const float flatResistance = 25000.0;	// resistance when flat
const float bendResistance = 100000.0;	// resistance at 90 deg

#define OLED_RESET     -1

OakOLED oled;

void resistance_and_bend_angle(int flexValue){

    float Vflex = flexValue * VCC / 1023.0;
    float Rflex = R_DIV * (VCC / Vflex - 1.0);
    Serial.println("Resistance: " + String(Rflex) + " ohms");
    // Use the calculated resistance to estimate the sensor's bend angle:
    float angle = map(Rflex, flatResistance, bendResistance, 0, 90.0);
    Serial.println("Bend: " + String(angle) + " degrees");
    Serial.println();
}


void setup() 
{ 
  Serial.begin(9600);
  // pinMode(flexPin0 ,INPUT);
  // pinMode(flexPin1 ,INPUT);
  // pinMode(flexPin2 ,INPUT);
  // pinMode(flexPin3 ,INPUT);
  // pinMode(flexPin4 ,INPUT);

  oled.begin();
  oled.clearDisplay();
  oled.setTextSize(2);
  oled.setTextColor(4);
  oled.setCursor(0, 0);
  oled.println("   TARP    \n  Project ");
  oled.display();
  delay(2000);


  oled.clearDisplay();
  oled.setTextSize(1);
  oled.setTextColor(1);
  oled.setCursor(0, 0);

  oled.println("Team Members :- \n");

  oled.println("Lavansh 20BCE1046");
  oled.display();
  delay(2000);

  
  oled.println("Dikshita 20BCE1056");
  oled.display();
  delay(2000);

  oled.println("Shubhangi 20BCE1161");
  oled.display();
  delay(2000);

  oled.println("Shrishti 20BCE1164");
  oled.display();
  delay(4000);
  
} 
 
void loop() 
{ 
  int flexValue0,flexValue1,flexValue2,flexValue3,flexValue4;
  flexValue0 = analogRead(flexPin0);
  flexValue1 = analogRead(flexPin1);
  flexValue2 = analogRead(flexPin2);
  flexValue3 = analogRead(flexPin3);

  Serial.print("Val 0: ");
  Serial.println(flexValue0);
  Serial.print("Val 1: ");
  Serial.println(flexValue1);
  Serial.print("Val 2: ");
  Serial.println(flexValue2);
  Serial.print("Val 3: ");
  Serial.println(flexValue3);


  if((flexValue0>=110 && flexValue0<=170) && (flexValue2>=110 && flexValue2<=170) && (flexValue3>=140 && flexValue3<=210) && (flexValue1 >= 130 && flexValue1 <= 190))
  { // all straight
    Serial.print("Straight condition\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Straight condition");
    oled.display();
    delay(2000);
  }
  else if((flexValue0>=110 && flexValue0<=170) && (flexValue2>=50 && flexValue2<=120) && (flexValue3>=50 && flexValue3<=120) && (flexValue1 >= 50 && flexValue1 <= 120))
  { // only thumb straight
    Serial.print("Good\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Good");
    oled.display();
    delay(2000);
  }
  else if((flexValue0>=50 && flexValue0<=120) && (flexValue2>=50 && flexValue2<=120) && (flexValue3>=140 && flexValue3<=210) && (flexValue1 >= 50 && flexValue1 <= 120))
  { // pinky open
    Serial.print("Sorry\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Sorry");
    oled.display();
    delay(2000);
  }
  else if((flexValue0>=50 && flexValue0<=120) && (flexValue2>=50 && flexValue2<=120) && (flexValue3>=50 && flexValue3<=120) && (flexValue1 >= 130 && flexValue1 <= 190))
  { // idx and middle open
    Serial.print("Peace\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Peace");
    oled.display();
    delay(2000);
  }
  else if((flexValue0>=110 && flexValue0<=170)  && (flexValue2>=50 && flexValue2<=120) && (flexValue3>=140 && flexValue3<=210) && (flexValue1 >= 50 && flexValue1 <= 120))
  { // ring and middle close
    Serial.print("Love\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Love");
    oled.display();
    delay(2000);
  }
  else if((flexValue0>=20 && flexValue0<=100)  && (flexValue2>=110 && flexValue2<=170) && (flexValue3>=140 && flexValue3<=210) && (flexValue1 >= 130 && flexValue1 <= 170))
  { // idx and thumb close
    Serial.print("Okay\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Okay");
    oled.display();
    delay(2000);
  }
  else
  {
    Serial.print("Symbol not added.\nPlease try another one.\n");
    oled.clearDisplay();
    oled.setTextSize(1);
    oled.setTextColor(1);
    oled.setCursor(0, 0);
    oled.println("Symbol yet to be added. Please try another one.");
    oled.display();
    delay(2000);
  }

}
