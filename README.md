# Laboratory Activity 5: Structured Workstation Light

**Name:** Rhea Leen Castor  
**Course:** BCA188 – Programming for Internet of Things  

## Objective

To control the brightness of an LED using a potentiometer while a push button is held.

When the button is released, both LEDs should turn off.

---

## Materials Used

- ESP32-WROOM Development Board (USB Type-C)
- USB Type-C Data Cable
- 10 kΩ Potentiometer
- Push Button
- 2 LEDs
- 2 × 330 Ω Resistors
- Breadboard
- Jumper Wires

---

## Circuit Wiring

### Potentiometer

| Pin | ESP32 Connection |
| :--- | :--- |
| VCC | 3V3 |
| SIGNAL | GPIO34 |
| GND | GND |

### Push Button

| Connection | ESP32 Connection |
| :--- | :--- |
| One side | GPIO23 |
| Other side | GND |

### Status LED

| Connection | ESP32 Connection |
| :--- | :--- |
| Anode (+) | GPIO18 through 330 Ω resistor |
| Cathode (-) | GND |

### PWM LED

| Connection | ESP32 Connection |
| :--- | :--- |
| Anode (+) | GPIO19 through 330 Ω resistor |
| Cathode (-) | GND |

---

## Inputs and Outputs

| Type | Device | GPIO |
| :--- | :--- | :---: |
| Input | Push Button | GPIO23 |
| Input | Potentiometer | GPIO34 |
| Output | Status LED | GPIO18 |
| Output | PWM LED | GPIO19 |

---

## Program Structure

The program uses separate functions for input, processing, and output.

- `readInputs()` reads the button and potentiometer.
- `processInputs()` decides the PWM value to use.
- `updateOutputs()` controls the two LEDs.
- `scaleToDuty(int raw)` converts the potentiometer reading from 0–4095 into a PWM value from 0–255.

Constants are used for the GPIO pin numbers.

The Boolean variable `buttonPressed` stores whether the button is pressed or released.

The numeric variables store the potentiometer reading and PWM values.

---

## Expected and Observed Results

| Test | Expected Result | Observed Result |
| :--- | :--- | :--- |
| Reset with button released | Both LEDs are OFF | Both LEDs were OFF |
| Hold the button | Status LED turns ON | Status LED turned ON |
| Low knob position while held | PWM LED is dim | PWM LED was dim |
| Middle knob position while held | PWM LED has medium brightness | PWM LED had medium brightness |
| High knob position while held | PWM LED is bright | PWM LED was bright |
| Rotate knob while button is released | PWM LED stays OFF | PWM LED stayed OFF |
| Release the button | Both LEDs turn OFF | Both LEDs turned OFF |

---

## Observation

The button worked as the enable control.

When the button was held, the status LED on GPIO18 stayed on, and the potentiometer controlled the brightness of the PWM LED on GPIO19.

When the button was released, both LEDs turned off. Rotating the potentiometer while the button was released did not turn on the PWM LED.

---

## Documentation

### Circuit Setup

[Insert image here]

### Button Released

[Insert image here]

### Button Held

[Insert image here]

### Low Brightness

[Insert image here]

### Middle Brightness

[Insert image here]

### High Brightness

[Insert image here]
