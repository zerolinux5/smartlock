#include <Servo.h>

Servo myServo;
int inPin = 7;
int currentMode = 0; //pulled out
boolean lastButton = LOW;
boolean currentButton = LOW;

void setup()
{
  pinMode(inPin, INPUT); 
  myServo.attach(9);
}

boolean debounce(boolean last)
{
    boolean current = digitalRead(inPin);
    if(last != current)
    {
      delay(5);
      current = digitalRead(inPin);  
    }
    return current;
}

void loop()
{
  currentButton = debounce(lastButton);
  if(lastButton == LOW && currentButton == HIGH){
    if (currentMode == 0){
      myServo.write(156);
      delay(15);
      currentMode = 1;  
    } else{
      myServo.write(80);
      delay(15);
      currentMode = 0;  
    }
  }
  lastButton = currentButton;
}
