# Codetech-task-1COMPANY: CODTECH IT SOLUTIONS

NAME: KANDHI AKHIL

INTERN ID: CT04DF1663

DOMAIN: Embedded Systems

DURATION: 4 WEEKS

MENTOR: Neela Santhosh Kumar 

DESCRIPTION: The Push Button Counter is a simple embedded systems project where a digital counter increases each time a button is pressed. It uses a microcontroller like Arduino to read the push button input and display the count on an LCD or OLED screen. A pull-down resistor is used to ensure stable input readings. Debouncing is implemented in code to prevent false triggering. This project helps in understanding digital input, output display interfacing, and basic programming logic. It is commonly used in applications like people counters, product counting systems, and digital scoreboards. It’s an ideal beginner-level project in electronics.

CIRCUIT DIAGRAM :
![17512049137413312857524127308616](https://github.com/user-attachments/assets/adb917d9-5c37-4452-aa91-959aca7863c5)

CODE: #include <LiquidCrystal.h>

// LCD pins: RS, E, D4, D5, D6, D7
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);

const int buttonPin = 2;
int counter = 0;
int buttonState = 0;
int lastButtonState = 0;

void setup() {
  pinMode(buttonPin, INPUT);
  lcd.begin(16, 2);
  lcd.print("Counter: ");
  lcd.setCursor(0, 1);
  lcd.print(counter);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH && lastButtonState == LOW) {
    counter++;
    lcd.setCursor(0, 1);
    lcd.print("                "); // Clear line
    lcd.setCursor(0, 1);
    lcd.print(counter);
    delay(200);  // Debounce delay
  }

  lastButtonState = buttonState;
}

OUTPUT:
![17512050946588447273061132638315](https://github.com/user-attachments/assets/d2ddc1b6-3f6d-4d28-8467-72f044264053)

WORKING DEMO:
https://youtu.be/hIQgd8ydFac?si=n8fogsGnqSqnytBo
