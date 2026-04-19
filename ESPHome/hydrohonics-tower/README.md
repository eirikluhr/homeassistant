# Hydrophonics tower

XIAO ESP32-C6 Wiring Diagram

Breakdown of the Critical Driver Circuit (Highlighted in the Image):
- XIAO D7 (GPIO17) Output: This pin provides the 3.3V "brain signal."
- Transistor (2N3904): We have explicitly detailed the pinout (Emitter, Base, Collector with the flat side facing you). This component performs the "heavy lifting" by electrically linking the 5V Relay IN pin to GND whenever the XIAO sends a 3.3V signal.
- The 1kΩ Base Resistor: This resistor is mandatory. It sits between XIAO D7 and the Base of the transistor, protecting your XIAO pin from drawing too much current.
- The 10kΩ Pull-Up (on Relay IN): As discussed, this resistor goes from the Relay IN pin up to the 5V rail. This is the key safety measure—it forces the 5V relay's signal "high" (OFF) whenever the transistor is not being actively switched by the XIAO, ensuring the pump stays OFF during reboots.

Other Components (Included for completeness):
- Manual Toggle Button: Connected simply between XIAO D6 (GPIO16) and GND. We use the XIAO's internal pull-up resistor (defined in the ESPHome YAML), so no extra external resistors are needed here.
- Status LED: Connected from XIAO D8 (GPIO19) through a 330Ω resistor to GND.
- With this circuit, your XIAO is now perfectly isolated from the 5V logic. Your ESPHome inverted: false logic will work as expected, and your pump controller will be robust and reliable.


![Wiring diagram](Gemini_Generated_Image_5mpslo5mpslo5mps.png)
