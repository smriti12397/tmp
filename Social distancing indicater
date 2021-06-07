const int trigPin = 9; //pin for sensor, trig pin transmits signal to object in front of it
const int echoPin = 10; //pin for sensor, echo pin receives the signal the object reflects and therefore the distance is measured
const int buzzPin = 2; //buzzer pin on arduino
long duration; //distance variable
int distance;
void setup()
{
Serial.begin(9600); 
pinMode(trigPin, OUTPUT); 
pinMode(echoPin, INPUT);
pinMode(buzzPin, OUTPUT);
}
void loop() {
digitalWrite(trigPin, LOW);
delayMicroseconds(2);
digitalWrite(trigPin, HIGH); //trigpin's output pulse
delayMicroseconds(1000);
digitalWrite(trigPin, LOW);
duration = pulseIn(echoPin, HIGH); //calibrate echo pin's pulse input
distance= duration*0.034/2; // distanceCm is half the duration multiplied by 0.034
Serial.println("Distance: "); //print to serial monitor
Serial.println(distance); //print distance in Cm to the serial monitor
delay(500); //so you don't get overloaded by serial monitor outputs


if (distance <= 150 && distance >= 0) { //if distance from sensor to object is less than 150cm and more than 0

digitalWrite(buzzPin, HIGH); //buzz
tone(2, 500, 120); //so we can hear a sound from the buzzer that isn't inaudible
//buzz 
} else {
//dont buzz 
digitalWrite(buzzPin, LOW); //don't buzz
}
}
