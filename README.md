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

<img width="4096" height="2304" alt="Unknown-6" src="https://github.com/user-attachments/assets/63548a74-8c20-437a-8334-636304942076" />

<img width="2048" height="1330" alt="Unknown-7" src="https://github.com/user-attachments/assets/f051d6c3-50c5-459c-98de-c212630e420b" />

<img width="2048" height="1330" alt="Unknown-8" src="https://github.com/user-attachments/assets/e300da38-8964-4e5c-a5f8-511735851b61" />

<img width="2048" height="1330" alt="Unknown-9" src="https://github.com/user-attachments/assets/736934c4-563c-4582-8cb4-9d5c7e88bb8e" />

<img width="2048" height="1330" alt="Unknown-10" src="https://github.com/user-attachments/assets/ce50c702-5034-4594-8293-07991b480e4f" />

<img width="2048" height="1330" alt="Unknown-11" src="https://github.com/user-attachments/assets/5437486d-9dc9-41f8-9ca4-1411a104ba7e" />

<img width="2048" height="1330" alt="Unknown-12" src="https://github.com/user-attachments/assets/5ed6ceee-47ed-4415-ab5f-5c1eb0a9a7c9" />

https://github.com/user-attachments/assets/df45f69a-fe38-4154-8b3e-2b562ced9f3e

https://github.com/user-attachments/assets/c8386101-eb64-47e9-9dc4-f1aaa23169b0

https://github.com/user-attachments/assets/78d650f9-69f2-452a-9fa7-4db7c3b146b9

https://github.com/user-attachments/assets/104b44d0-50d5-4425-a81a-c8249a40736d

https://github.com/user-attachments/assets/88bbb5f8-7e3f-47e7-8089-fc5a3a140375
