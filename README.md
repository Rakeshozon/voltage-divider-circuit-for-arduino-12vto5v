# Voltage Divider Circuit (12V to 5V Converter)

This repository contains a voltage divider circuit designed to convert 12V to 5V using a simple resistor-based voltage divider. The circuit was built using Tinkercad, and the schematic is included in this repository.

## Circuit Overview

The voltage divider circuit consists of two resistors (10KΩ and 7KΩ) to step down a 12V input voltage to approximately 5V, making it suitable for use with microcontrollers like Arduino.

### Components Used:
- **Power Supply**: 12V source
- **Resistors**:
  - 10KΩ (R1)
  - 7KΩ (R2) *(You can use 6.8KΩ as 7KΩ is difficult to find)*
- **Arduino Uno** (for measuring output voltage)
- **Multimeter** (for verification)
- **Connecting Wires**

## Circuit Design

The voltage divider formula is:

\[ V_{out} = V_{in} \times \frac{R2}{(R1 + R2)} \]

Substituting the values:

\[ V_{out} = 12V \times \frac{7KΩ}{(10KΩ + 7KΩ)} \]

\[ V_{out} \approx 4.94V \] (which is close to 5V)

## Steps to Build in Tinkercad

1. **Open Tinkercad** and create a new circuit.
2. **Add Components**:
   - Drag and drop a **12V power supply**.
   - Place two resistors **(10KΩ and 7KΩ in series)**.
   - Connect the junction of the resistors to an **Arduino analog pin (A0)**.
3. **Connections**:
   - Connect **one end of the 10KΩ resistor to the 12V source**.
   - Connect **the other end to one side of the 7KΩ resistor**.
   - Connect **the free end of the 7KΩ resistor to GND**.
   - Connect **the middle junction of the resistors to the Arduino analog input (A0)**.
4. **Verify the Output**:
   - Use a **multimeter** to check the output voltage at the junction.
   - It should read approximately **5V**.
5. **Code for Arduino (Optional)**:
   
   You can use this code if your Arduino supports 12V.
   ```cpp
   void setup() {
       Serial.begin(9600);
   }
   
   void loop() {
       int sensorValue = analogRead(A0);
       float voltage = sensorValue * (5.0 / 1023.0) * (17.0 / 7.0); // Convert to 12V scale
       Serial.println(voltage);
       delay(1000);
   }
   ```

## Notes:
- If **7KΩ is unavailable**, use **6.8KΩ**, which is a standard value.
- This method is suitable for low-power applications but not ideal for high-current loads.
- For **better efficiency**, consider using a **buck converter** instead of a resistor divider.

## Conclusion
This voltage divider circuit provides a simple way to convert 12V to 5V for low-power applications. It is useful for interfacing sensors or microcontrollers with higher voltage sources. The Tinkercad simulation helps visualize and test the circuit before implementing it in real hardware.

---

### Repository Files
- **`README.md`** (This file)
- **Tinkercad Simulation Screenshot** (Included in the repo for reference)

