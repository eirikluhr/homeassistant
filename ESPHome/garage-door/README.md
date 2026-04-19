# Garage door controller and monitoring

| Component       | XIAO C6 Pin | Connection Type      | Hardware Requirement      | Notes      |
| --------------- | ----------- | -------------------- | ------------------------- | ---------- |
|Door 1 Trigger   | GPIO16      | Output (Digital) | 220Ω Resistor | Connects to Optoisolator 1 Input (+) |
|Door 1 Trigger   | GPIO16      | Output (Digital) | 220Ω Resistor | Connects to Optoisolator 1 Input (+) |
|Door 2 Trigger   | GPIO23      | Output (Digital) | 220Ω Resistor | Connects to Optoisolator 2 Input (+) |
|Door 1 Sensor    | GPIO17      | Input (Pullup) | Magnetic Reed Switch | Connects GPIO17 to GND when closed |
|Door 2 Sensor    | GPIO19      | Input (Pullup) | Magnetic Reed Switch | Connects GPIO19 to GND when closed |
|Common Ground    | GND         | Power Rail | Common Wire | Tie all sensor and opto (-) wires here |
|Power Supply     | 5V / USB    | Power Input | USB-C Cable | 5V 1A adapter is sufficient |


Hardware Implementation Tips:
The Resistors: It is critical to keep the 220Ω resistors on GPIO16 and GPIO23. The XIAO C6 uses 3.3V logic; without these resistors, the optoisolator's internal LED can draw too much current and potentially burn out the GPIO pins.

Optoisolator Orientation: On the "input" side of the optoisolator, ensure the current flows from the GPIO pin (Anode) through the resistor to the optoisolator, then back to the XIAO's GND (Cathode).

Reed Switch Mounting: Since garage doors can vibrate or shift in the wind, ensure your magnets are mounted firmly so that the "Closed" signal remains stable when the door is latched.

![Wiring diagram](Gemini_Generated_Image_zeqa4izeqa4izeqa.png)
