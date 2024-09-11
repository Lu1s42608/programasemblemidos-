# programasemblemidos-
const int motorPin = 9;    // Pin de control del transistor
const int joystickXPin = A0; // Pin analógico para el eje X del joystick

void setup() {
  pinMode(motorPin, OUTPUT);
  pinMode(joystickXPin, INPUT);
}

void loop() {
  int joystickXValue = analogRead(joystickXPin); // Leer el valor del eje X del joystick

  // Mapear el valor del joystick (0-1023) al rango de PWM (0-255)
  int motorSpeed = map(joystickXValue, 0, 1023, 0, 255);

  // Ajustar la velocidad del motor
  analogWrite(motorPin, motorSpeed);

  delay(10); // Pequeña espera para estabilizar la lectura
}
