# arduino-traffic-light-north-south
North–South traffic light control system using Arduino
// North-South Traffic Light System

int northRed = 2;
int northYellow = 3;
int northGreen = 4;

int southRed = 5;
int southYellow = 6;
int southGreen = 7;


void setup() {
  pinMode(northRed, OUTPUT);
  pinMode(northYellow, OUTPUT);
  pinMode(northGreen, OUTPUT);

  pinMode(southRed, OUTPUT);
  pinMode(southYellow, OUTPUT);
  pinMode(southGreen, OUTPUT);
}

void loop() {
  digitalWrite(northGreen, HIGH);
  digitalWrite(southRed, HIGH);
  delay(5000);

  digitalWrite(northGreen, LOW);
  digitalWrite(northYellow, HIGH);
  delay(2000);

  digitalWrite(northYellow, LOW);
  digitalWrite(northRed, HIGH);
  digitalWrite(southRed, LOW);
  digitalWrite(southGreen, HIGH);
  delay(5000);

  digitalWrite(southGreen, LOW);
  digitalWrite(southYellow, HIGH);
  delay(2000);

  digitalWrite(southYellow, LOW);
  digitalWrite(southRed, HIGH);
  digitalWrite(northRed, LOW);
}
