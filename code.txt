const int sensorMin = 0; 
const int sensorMax = 1024; 
void setup() 
{
  pinMode(2, INPUT);
  Serial.begin(9600);
}

void loop()
{
  int sensorReading = analogRead(A0);
  int tilt=digitalRead(2);
  int range = map(sensorReading, sensorMin, sensorMax, 0, 3);

  switch (range)
    {
      case 0:
        Serial.println("RAINING");
        break;

      case 1:
        Serial.println("RAIN WARNING");
        break;

      case 2:
        Serial.println("NOT RAINING");
        break;
    }
    Serial.println("tilt:");
    Serial.println(tilt);
  delay(1000); 
}