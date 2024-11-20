// Define the pins for all buttons
#define btn1pin A3
#define btn2pin A2
#define btn3pin A0
#define btn4pin A1

// Define the initial state as false
boolean state = false;

// Initialize button press counters
int btn1 = 0;
int btn2 = 0;
int btn3 = 0;

// Initialize button state trackers
boolean btn1state = false;
boolean btn2state = false;
boolean btn3state = false;

// Initialize LED state tracker
boolean LED_ON = false;

void setup() {
  // Set LED pins as outputs
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(11, OUTPUT);

  // Initialize all LED pins to LOW (off)
  digitalWrite(6, LOW);
  digitalWrite(7, LOW);
  digitalWrite(8, LOW);
  digitalWrite(9, LOW);
  digitalWrite(10, LOW);
  digitalWrite(11, LOW);

  // Start serial communication for debugging
  Serial.begin(9600);
}

void loop() {
  // Check if button 1 is pressed
  if (digitalRead(btn1pin) == LOW) {
    if (btn1state == false) {
      btn1++;  // Increment button 1 counter
      btn1state = true;  // Set button 1 state to pressed
    }
  }

  // Check if button 2 is pressed
  if (digitalRead(btn2pin) == LOW) {
    if (btn2state == false) {
      btn2++;  // Increment button 2 counter
      btn2state = true;  // Set button 2 state to pressed
    }
  }

  // Check if button 3 is pressed
  if (digitalRead(btn3pin) == LOW) {
    if (btn3state == false) {
      btn3++;  // Increment button 3 counter
      btn3state = true;  // Set button 3 state to pressed
    }
  }

  // Reset button 1 state when released
  if (digitalRead(btn1pin) == HIGH) {
    btn1state = false;
  }

  // Reset button 2 state when released
  if (digitalRead(btn2pin) == HIGH) {
    btn2state = false;
  }

  // Reset button 3 state when released
  if (digitalRead(btn3pin) == HIGH) {
    btn3state = false;
  }

  // Check if button 4 is pressed to activate recipes
  if (digitalRead(btn4pin) == LOW) {
    if (state == false) {
      state = true;

      if (LED_ON == false) {
        // Recipe for Indian Chickpeas (Chole)
        if (btn1 == 1 && btn2 == 2 && btn3 == 2) {
          LED_ON = true;
          digitalWrite(9, LOW);
          digitalWrite(10, HIGH);
          digitalWrite(11, HIGH);
          digitalWrite(6, HIGH);
          digitalWrite(7, HIGH);
          digitalWrite(8, HIGH);
        }

        // Recipe for Cumin Potato
        if (btn1 == 2 && btn2 == 2 && btn3 == 2) {
          LED_ON = true;
          digitalWrite(9, LOW);
          digitalWrite(10, HIGH);
          digitalWrite(11, HIGH);
          digitalWrite(6, HIGH);
          digitalWrite(7, LOW);
          digitalWrite(8, LOW);
        }

        // Recipe for Okra Curry Indian Style
        if (btn1 == 3 && btn2 == 2 && btn3 == 2) {
          LED_ON = true;
          digitalWrite(9, LOW);
          digitalWrite(10, HIGH);
          digitalWrite(11, HIGH);
          digitalWrite(6, LOW);
          digitalWrite(7, HIGH);
          digitalWrite(8, HIGH);
        }
      } else if (LED_ON == true) {
        LED_ON = false;
        // Turn off all LEDs
        digitalWrite(6, LOW);
        digitalWrite(7, LOW);
        digitalWrite(8, LOW);
        digitalWrite(9, LOW);
        digitalWrite(10, LOW);
        digitalWrite(11, LOW);
        // Reset button counters
        btn1 = 0;
        btn2 = 0;
        btn3 = 0;
      }
    }
  }

  // Reset state when button 4 is released
  if (digitalRead(btn4pin) == HIGH) {
    state = false;
  }

  // Print button counters for debugging
  Serial.print(btn1);
  Serial.print("   ");
  Serial.print(btn2);
  Serial.print("   ");
  Serial.println(btn3);
}
