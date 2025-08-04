// Motor 1 pins

#define IN1 8

#define IN2 9

// Motor 2 pins

#define IN3 10

#define IN4 11

// IR sensor pin

#define IRSENSOR 7 // Using digital pin 7

void setup() {

 pinMode(IN1, OUTPUT);

 pinMode(IN2, OUTPUT);

 pinMode(IN3, OUTPUT);

 pinMode(IN4, OUTPUT);

 pinMode(IRSENSOR, INPUT);

 Serial.begin(9600);

}

void loop() {

 int sensorValue = digitalRead(IRSENSOR); // Read digital value from IR sensor

 if (sensorValue == LOW) { // Obstacle detected

 // Move both motors backward

 digitalWrite(IN1, LOW);

 digitalWrite(IN2, HIGH);

 digitalWrite(IN3, LOW);

 digitalWrite(IN4, HIGH);

 Serial.println("Obstacle detected! Moving backward.");

 } else { // No obstacle

 // Move both motors forward

 digitalWrite(IN1, HIGH);

 digitalWrite(IN2, LOW);

 digitalWrite(IN3, HIGH);

 digitalWrite(IN4, LOW);

 Serial.println("Path clear! Moving forward.");

 }

 delay(100); // Small delay for stability
 }
