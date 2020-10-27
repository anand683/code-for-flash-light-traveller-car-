//# code-for-flash-light-traveller-car-
//lets discover pro
#include <AFMotor.h>
AF_DCMotor motor(1);
AF_DCMotor motor1(2);
AF_DCMotor motor3(3);
AF_DCMotor motor4(4);
int ldr1=A1;
int ldr2=A3;
int ldr3=A4;
int ldr4=A5;
void setup(){
  pinMode(ldr1,INPUT);
  pinMode(ldr2,INPUT);
   pinMode(ldr3,INPUT);
  pinMode(ldr4,INPUT);
  motor.setSpeed(200);
  motor.run(RELEASE);
  motor1.setSpeed(200);
  motor1.run(RELEASE);
  motor3.setSpeed(200);
  motor3.run(RELEASE);
  motor4.setSpeed(200);
  motor4.run(RELEASE);
  Serial.begin(9600);
}
void loop(){
  int val=analogRead(ldr1);
  int val1=analogRead(ldr2);
  int val2=analogRead(ldr3);
  int val3=analogRead(ldr4);
  if(val>=500){
    motor.run(FORWARD);
    motor1.run(FORWARD);
    motor3.run(FORWARD);
    motor4.run(FORWARD);
  }
  
  
  else if(val3>=400){
    motor.run(BACKWARD);
    motor1.run(BACKWARD);
     motor3.run(BACKWARD);
    motor4.run(BACKWARD);
  }
   else if(val2>=100){
    motor.run(RELEASE);
    motor1.run(RELEASE);
    motor3.run(FORWARD);
    motor4.run(FORWARD);
  }
   else if(val1>=400){
    motor.run(FORWARD);
    motor1.run(FORWARD);
    motor3.run(RELEASE);
    motor4.run(RELEASE);
  }
  else 
  {
    motor.run(RELEASE);
    motor1.run(RELEASE);
    motor3.run(RELEASE);
    motor4.run(RELEASE);
  }
 
}
