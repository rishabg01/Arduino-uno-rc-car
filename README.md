
// Starting of Program
#include<SoftwareSerial.h>
int Input_Pin_4 = 9;
int Input_Pin_3 = 10;
int Input_Pin_2 = 11;
int Input_Pin_1 = 12;
char Value;
void setup() {
  pinMode(Input_Pin_4, OUTPUT);  // Digital pin 9
  pinMode(Input_Pin_3, OUTPUT);  // Digital pin 10
  pinMode(Input_Pin_2, OUTPUT);  // Digital pin 11
  pinMode(Input_Pin_1, OUTPUT);  // Digital pin 12
  Serial.begin(9600);
}
void loop() {
  while (Serial.available() > 0) {
    Value = Serial.read();
    Serial.println(Value);
  }
  if ( Value == 'F') {
    // Robo Pe_t Run Forward
    digitalWrite(Input_Pin_1, HIGH);
    digitalWrite(Input_Pin_2, LOW);
    digitalWrite(Input_Pin_3, HIGH);
    digitalWrite(Input_Pin_4, LOW);
  } else if (Value == 'B') {
    //Robo Pet Run Backward
    digitalWrite(Input_Pin_1, LOW);
    digitalWrite(Input_Pin_2, HIGH);
    digitalWrite(Input_Pin_3, LOW);
    digitalWrite(Input_Pin_4, HIGH);
  } else if (Value == 'L') {
    //Robo Pet Turn Left
    digitalWrite(Input_Pin_1, LOW);
    digitalWrite(Input_Pin_2, LOW);
    digitalWrite(Input_Pin_3, HIGH);
    digitalWrite(Input_Pin_4, LOW);
  } else if (Value == 'R') {
    //Robo Pet Turn Right
    digitalWrite(Input_Pin_1, HIGH);
    digitalWrite(Input_Pin_2, LOW);
    digitalWrite(Input_Pin_3, LOW);
    digitalWrite(Input_Pin_4, LOW);
  } else if (Value == 'S') {
    //Robo Pet Stop
    digitalWrite(Input_Pin_1, LOW);
    digitalWrite(Input_Pin_2, LOW);
    digitalWrite(Input_Pin_3, LOW);
    digitalWrite(Input_Pin_4, LOW);
  }
}
