capsule-x-
==========
#include <IRremote.h>
int receiverpin=11;
int red = 13;
int yellow = 12;
int green = 10;
int blue = 8;
int red3 = 6;
int yellow3 = 7;
int green3 = 9;
int red4 = 5;
int yellow4 = 4;
int green4 = 3;
int red2 = 2;
int yellow2 = 1;
int green2 = 0;
int potPin = 2;  
int val = 0;
int flicker[] = {180, 30, 23, 255, 200, 180, 45, 90};




IRrecv irrecv(receiverpin);
decode_results results;
void setup(){
  irrecv.enableIRIn();
  pinMode(red,OUTPUT);
  pinMode(yellow,OUTPUT);
  pinMode(green,OUTPUT);
  pinMode(blue,OUTPUT);
  pinMode(red2,OUTPUT);
  pinMode(yellow2,OUTPUT);
  pinMode(green2,OUTPUT);
  pinMode(red3,OUTPUT);
  pinMode(yellow3,OUTPUT);
  pinMode(green3,OUTPUT);
  pinMode(red4,OUTPUT);
  pinMode(yellow4,OUTPUT);
  pinMode(green4,OUTPUT);
  
}
void loop(){
  val = analogRead(potPin);
  if(irrecv.decode(&results)){
    if (results.value==0x10){
    digitalWrite(red,HIGH);
    delay(val);
    digitalWrite(red,LOW);
    delay(val);
    digitalWrite(yellow,HIGH);
    delay(val);
    digitalWrite(yellow,LOW);
    delay(val);
    digitalWrite(green,HIGH);
    delay(val);
    digitalWrite(green,LOW);
    delay(val);
  }
   else if (results.value==0x810){
    digitalWrite(red2,HIGH);
    delay(val);
    digitalWrite(red2,LOW);
    delay(val);
    digitalWrite(yellow2,HIGH);
    delay(val);
    digitalWrite(yellow2,LOW);
    delay(val);
    digitalWrite(green2,HIGH);
    delay(val);
    digitalWrite(green2,LOW);
    delay(val);
  }
  else if (results.value==0x410){
    digitalWrite(red3,HIGH);
    delay(val);
    digitalWrite(red3,LOW);
    delay(val);
    digitalWrite(yellow3,HIGH);
    delay(val);
    digitalWrite(yellow3,LOW);
    digitalWrite(green3,HIGH);
    delay(val);
    digitalWrite(green3,LOW);
    delay(val);
  }
  else if (results.value==0xC10){
    digitalWrite(red4,HIGH);
    delay(val);
    digitalWrite(red4,LOW);
    delay(val);
    digitalWrite(yellow4,HIGH);
    delay(val);
    digitalWrite(yellow4,LOW);
    delay(val);
    digitalWrite(green4,HIGH);
    delay(val);
    digitalWrite(green4,LOW);
    delay(val);
  }
    else if (results.value==0x290){
      for(int i=0; i<7; i++){
      digitalWrite(blue, flicker[i]);
      delay(val);
      digitalWrite(blue,LOW);
      delay(200);
  }
    }
  
  for(int z = 0;z<2;z++){
  irrecv.resume();
}
  }
}



