capsule-x-
==========
int potPin = 2;    
int redled = 13; 
int yellowled = 12;
int greenled = 10;
int blueled = 8;
int val = 0;       
void setup() {
  pinMode(redled, OUTPUT);
  pinMode(yellowled, OUTPUT);
  pinMode(greenled, OUTPUT);
  pinMode(blueled, OUTPUT);
}

void loop() {
  val = analogRead(potPin);
  digitalWrite(redled, HIGH);
  delay(val);
  digitalWrite(redled, LOW);   
  delay(val);
  digitalWrite(yellowled, HIGH);
  delay(val);
  digitalWrite(yellowled, LOW);
  delay(val);
  digitalWrite(greenled, HIGH);
  delay(val);
  digitalWrite(greenled, LOW);
  delay(val);
  digitalWrite(blueled, HIGH);
  delay(val);
  digitalWrite(blueled, LOW);
  delay(val);
}
