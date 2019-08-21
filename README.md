# Agriculture_securer_system
// Energia code for project
#include<msp430.h>

void sendsms()
{
Serial.println("AT\r");
delay(100);
Serial.println("AT+CMGF=1\r");
delay(100);
Serial.println("AT+CMGS=\"9945501478\"\r");
delay(100);
Serial.println("DANGER!!!!");
delay(100);
Serial.println((char)26);
delay(100);
}
void setup(){
    Serial.begin(9600);
  
}

void loop(){
  int ldrValue=analogRead(A3);
 Serial.println(ldrValue);
if(ldrValue>1000)
 {
  sendsms();

 }
