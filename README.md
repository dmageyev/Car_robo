#include <SoftwareSerial.h>
SoftwareSerial bt(2,3);
char val=' ';

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  bt.begin(9600);
  for (int i=5;i<=10;i++) pinMode(i,OUTPUT);
}

void forward() {
  analogWrite(5, 255);
  analogWrite(10, 255);
  digitalWrite(6, LOW);
  digitalWrite(7, HIGH);
  digitalWrite(8, HIGH);
  digitalWrite(9, LOW);
}

void backward() {
  analogWrite(5, 255);
  analogWrite(10, 255);
  digitalWrite(6, HIGH);
  digitalWrite(7, LOW);
  digitalWrite(8, LOW);
  digitalWrite(9, HIGH);
}

void stp() {
  analogWrite(5, 0);
  analogWrite(10, 0);
  digitalWrite(6, LOW);
  digitalWrite(7, LOW);
  digitalWrite(8, LOW);
  digitalWrite(9, LOW);
}

void left() {
  analogWrite(5, 200);
  analogWrite(10, 200);
  digitalWrite(6, LOW);
  digitalWrite(7, HIGH);
  digitalWrite(8, LOW);
  digitalWrite(9, HIGH);
}

void right() {
  analogWrite(5, 200);
  analogWrite(10, 200);
  digitalWrite(6, HIGH);
  digitalWrite(7, LOW);
  digitalWrite(8, HIGH);
  digitalWrite(9, LOW);
}

void loop() {
  // put your main code here, to run repeatedly:
  if (bt.available()){
    val = bt.read();
    Serial.println("R-> " + String(val));
    
    // Обробник отриманих команд через Bluetooth
    
}
