Components:

    Arduino Nano
    Flame Sensor (140C001)
    Buzzer
    LED
    Resistor (220Ω for the LED)
    Connecting wires
    Breadboard

Connections:

    Flame Sensor:
        VCC to 5V on Arduino Nano
        GND to GND on Arduino Nano
        D0 (Digital Output) to a digital pin on Arduino Nano (e.g., D7)

    Buzzer:
        Positive (longer leg) to a digital pin on Arduino Nano (e.g., D12)
        Negative (shorter leg) to GND on Arduino Nano

    LED:
        Anode (longer leg) to a digital pin on Arduino Nano (e.g., D4) through a 220Ω resistor
        Cathode (shorter leg) to GND on Arduino Nano
Explanation:

    Setup Function:
        pinMode(flameSensorPin, INPUT); sets the flame sensor pin as an input.
        pinMode(buzzerPin, OUTPUT); sets the buzzer pin as an output.
        pinMode(ledPin, OUTPUT); sets the LED pin as an output.
        digitalWrite(buzzerPin, LOW); ensures the buzzer is off at the start.
        digitalWrite(ledPin, LOW); ensures the LED is off at the start.
        Serial.begin(9600); initializes the serial communication at 9600 bps.

    Loop Function:
        int flameState = digitalRead(flameSensorPin); reads the state of the flame sensor.
        If a flame is detected (flameState == LOW), the buzzer and LED are turned on (digitalWrite(buzzerPin, HIGH); and digitalWrite(ledPin, HIGH);).
        If no flame is detected, the buzzer and LED are turned off (digitalWrite(buzzerPin, LOW); and digitalWrite(ledPin, LOW);).
        Serial.println("Flame detected!"); and Serial.println("No flame."); print the status to the Serial Monitor for debugging.
