# Ultrasonic Sensor to find out the Distance

```C
#define ECHOPin 5
#define TRIGPin 6
long duration;
int distance;

void setup() {
  pinMode(TRIGPin, OUTPUT);
  pinMode(ECHOPin, INPUT);
  Serial.begin(9600);
  Serial.print("Testing of the Ultrasonic sensor HC-SR04");
  Serial.print("With Arduino UNO R3 board");
}

void loop() {
  digitalWrite(TRIGPin, LOW);
  delayMicroseconds(4);
  digitalWrite(TRIGPin, HIGH);
  delayMicroseconds(15);
  digitalWrite(TRIGPin, LOW);
  duration = pulseIn(ECHOPin, HIGH);
  distance = duration * (0.034/2);
  Serial.print("Distance : ");
  Serial.print(distance);
  Serial.print(" cm");
}
```

# IR Sensor with LED ( Object detection )

```C
int sensorPin = 2;
int outputPin = 13;

void setup(){
  pinMode(sensorPin, INPUT);
  pinMode(outputPin, OUTPUT);
  Serial.begin(9600);
}

void loop(){
  int sensorValue = digitalRead(sensorPin);
  Serial.print("Sensor Value : ");
  Serial.print(sensorValue);
  delay(1000);
  if(sensorValue == LOW){
    digitalWrite(outputPin, HIGH);
  }
  else{
    digitalWrite(outputPin, LOW);
  }
}
```
