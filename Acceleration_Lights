
#include <Adafruit_CircuitPlayground.h>

unsigned long currentTime;
unsigned long tempTime = 0;
int delayTime = 5000;
bool lightFlag = false;

void setup() {
  // put your setup code here, to run once:
  CircuitPlayground.begin();
  Serial.begin(9600);
}

void loop() 
{

  currentTime = millis();
  // put your main code here, to run repeatedly:
  float x = CircuitPlayground.motionX();
  if (x > 12.3 && x < 15 && lightFlag == false)
  {
    for (int i = 0; i < 10; i++)
    {
      CircuitPlayground.setPixelColor(i, 255, 255, 255);
      tempTime = millis();
      lightFlag = true;
    }
  }

  
  if (lightFlag == true && currentTime - tempTime >= 5000)
  {
    for (int i = 0; i < 10; i++)
    {
      CircuitPlayground.setPixelColor(i, 0, 0, 0);
      lightFlag = false;
    }
  }
  Serial.println(currentTime - tempTime);
  
}
