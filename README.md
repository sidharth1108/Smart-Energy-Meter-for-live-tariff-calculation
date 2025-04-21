#  Smart Energy Meter for Live Tariff Calculation

A real-time energy monitoring system using Arduino, PZEM-004T, and an I2C LCD. It displays voltage, current, power, energy, and calculates tariff based on consumption slabs.

---

## What it does:

- Real-time display of:
  - Voltage
  - Current
  - Real Power
  - Energy (kWh)
  - Frequency
  - Power Factor
  - Reactive & Apparent Power
- An example Tariff Calculation(1 unit = 0.001KWH):
  - `0–5 units:` ₹2/unit  
  - `5–10 units:` ₹3.5/unit  
  - `10–15 units:` ₹5/unit  
  - `>15 units:` ₹8/unit
  (Change it according to your needs)
- I2C LCD display with 5 display modes (toggled via a push-button)
- Serial Monitor output for debugging/logging

---

## Components Required

- Arduino UNO / Nano / Mega
- PZEM-004T V3.0 module
- 16x2 I2C LCD display
- Push-button (for mode switching)
- Jumper wires and breadboard
- Resistors (optional, for button pull-down)

---

## Hardware Connections

### Arduino to PZEM-004T 

| PZEM Pin | Arduino Pin           |
|----------|------------------------|
| TX       | D8 (SoftwareSerial RX) |
| RX       | D9 (SoftwareSerial TX) |
| GND      | GND                    |
| VCC      | 5V                     |

>Note: Refer this for further information regarding specifications and connection to load: [`Data sheet`](https://innovatorsguru.com/wp-content/uploads/2019/06/PZEM-004T-V3.0-Datasheet-User-Manual.pdf)

### I2C LCD to Arduino

| LCD Pin | Arduino Pin    |
|---------|----------------|
| SDA     | A4             |
| SCL     | A5             |
| VCC     | 5V             |
| GND     | GND            |

### Push-button to Arduino

| Button Pin | Arduino Pin |
|------------|-------------|
| One End    | D4          |
| Other End  | GND         |

> Note: The button uses `INPUT_PULLUP` in the code. No external pull-up resistor needed.

---

## Setup Instructions

1. Clone or download this repository.
2. Open the Arduino IDE and install the following libraries:
   - [`PZEM004Tv30`](https://github.com/olehs/PZEM004T)
   - [`LiquidCrystal_I2C`](https://github.com/johnrickman/LiquidCrystal_I2C)
3. Upload the provided code to your Arduino board.
4. Connect the hardware as per the tables above.
5. Open the **Serial Monitor** at **9600 baud** to view real-time readings.
6. Use the **push-button** to cycle through display modes on the LCD.

---

## Author

Made by Sidharth

---

## License

This project is licensed under the [MIT License](LICENSE).
