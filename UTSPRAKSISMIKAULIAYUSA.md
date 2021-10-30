# UTSPRAKSISMIKAULIA

//Nama : Aulia Yusa
//NIM : 1197070016
//UTS Praktikum Sistem Mikroprosesor


#include <LiquidCrystal.h>
#include <Servo.h>

LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
Servo servo1;
int servoPin = 9;
int lightSensorPin = A0;


void setup() {
  servo1.attach(9);
  servo1.write (0) ;
  lcd.begin(16, 2);
  lcd.print("jendela terbuka");
  pinMode(lightSensorPin, INPUT);
  Serial.begin(9600);
  
}

void loop() {
  
  if (digitalRead(lightSensorPin)== LOW)
  {
     servo1.write (90);;
    delay (500);
  }
  else
  {
  servo1.write(0); 
    delay (500);
    lcd.clear ();
    lcd.setCursor (0,0);
    lcd.print ("jendela tertutup");
    delay (500);
    
  }
  }
 
