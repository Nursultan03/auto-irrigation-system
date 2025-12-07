# Project Description:

This project is an automated irrigation system designed for home gardening. The system uses soil moisture sensors, an Arduino, and a submersible water pump to automatically water plants when soil moisture drops below a certain point (30% in our case).


# Features:

• Automatic watering based on soil moisture

• Real-time monitoring using soil moisture sensor

• I2C LCD display



# Hardware Used:

• Arduino Uno

• Soil moisture sensor

• MOSFET

• Relay module

• Water pump

• Jumper wires

• Tubing + Reservoir

# Setup:

1. 🧠 Power FoundationCommon Ground is key: The Arduino GND must be connected to the MOSFET/Battery GND.

Arduino Power: Powered via USB (or its own power source).

Pump Power: Powered by separate 6V batteries (or power supply).

2. 💪 Pump and MOSFET (The Muscle)This is where the "Brain" controls the "Power.

"MOSFET Wiring (LR7843 / D4184 Module):Thick Wires (Power Input):+ (Vin): Connect to Battery Positive (+) (6V).
- (GND): Connect to Battery Negative (-).
- Thick Wires (Pump Output):OUT +: Connect to the Pump's Red wire.
- OUT -: Connect to the Pump's Black wire.
- Thin Wires (Control from Arduino):PWM / SIG (Yellow): Connect to Arduino Pin D9.
- GND (Black): Connect to Arduino GND.

- ⚡ PROTECTION (Flyback Diode):The diode is screwed/soldered directly to the Pump's contacts (parallel).
- Side WITH the Stripe (Ring): Connect to Pump Positive (+).
- Side WITHOUT the Stripe: Connect to Pump Negative (-).
  This prevents the screen from glitching when the pump stops.

3. 👀 Red Sensor (Moisture Level)The sensor that dictates the logic "Dry -> Water".

   VCC (+): Connect to Arduino 5V.

   GND (-): Connect to Arduino GND.

   S (Signal): Connect to Arduino Pin A0.

5. 📺 LCD Screen (1602 + I2C)To see the percentage and status.

   GND: Connect to Arduino GND.

   VCC: Connect to Arduino 5V.

   SDA: Connect to Arduino Pin A4.

   SCL: Connect to Arduino Pin A5.
  
📋 Final Pin Summary Table

Arduino Pin Connected To D9 

MOSFET (SIG) Controls the Pump

A0 Red Sensor (S) Reads Soil Moisture

A4 LCD Screen (SDA) Display Data

5V Sensor & Screen Power for low-voltage parts

GND EVERYTHING Common Ground for all parts

![telegram-cloud-photo-size-2-5310186544624766616-w](https://github.com/user-attachments/assets/4e1c6712-381f-41dd-8cae-0fe0e7bd04de)

