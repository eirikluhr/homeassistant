# Hydrophonics tower

XIAO ESP32-C6 Wiring Diagram

Component,ESPHome GPIO,XIAO Physical Label,Wiring Instruction
Relay Signal,GPIO 17,D7,Connect D7 to the IN pin on your relay module.
Status LED,GPIO 19,D8,Connect D8 → 330Ω Resistor → LED (+) → GND.
Toggle Button,GPIO 16,D6,Connect D6 → Momentary Button → GND.
Common Ground,GND,GND,Ensure all components share a connection to a XIAO GND pin.
Power Input,5V / VIN,5V,Provide power via USB-C or the 5V pin.

Pro-Tips for the XIAO Form Factor:
- Level Shifting: The XIAO series is strictly 3.3V logic. If your relay module is designed for 5V "High Level" triggers, it might be "flaky" when triggered by the XIAO's 3.3V pins. If the pump doesn't click on, you may need a relay that specifically supports 3.3V signals.
- Pull-up Resistors: In the YAML I provided, I used mode: INPUT_PULLUP for the button on GPIO 16. This uses the XIAO's internal resistor, so you do not need to add an external resistor to your button circuit.
- Soldering vs. Breadboard: For a water pump project, I highly recommend soldering your connections or using the XIAO "Screw Terminal" expansion board. Breadboard jumpers can vibrate loose over time, especially if the pump causes any mechanical vibration nearby.
