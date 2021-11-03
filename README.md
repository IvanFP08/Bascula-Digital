#include <LiquidCrystal.h>
LiquidCrystal lcd(12,11,5,4,3,2);
double F = 0.0;
double peso=0.0;
double v = 0.0;
double r = 0.0;
void setup() {
lcd.begin(16, 2);
pinMode(A0, INPUT);
Serial.begin(9600);
}void loop() {
v=analogRead(A0)*(5.0/1023.0);
r=10000*((5/v)-1);
F=pow((r/6029.6),(1/-.703));
peso=(F/9.81)*1000;
lcd.setCursor(0, 0);
lcd.print("F=");
lcd.print(F,2);
lcd.print("N");
lcd.setCursor(0, 1);
lcd.print("Peso=");
lcd.print(peso,2);
lcd.print("g");
delay(1000);
lcd.clear();
}
