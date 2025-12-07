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


# Usage Instructions

1. System Overview

System consists of:

– Water reservoir with a submersible pump inside

– Soil container with a moisture sensor inserted

Arduino + MOSFET – Controls and powers the system

Silicone tubing – Carries water from the pump to the soil

When the soil becomes dry, the moisture sensor detects it and signals the Arduino, which turns on the pump and waters the soil automatically.

2. Before First Use

Step 1 — Fill the Water Reservoir

Open reservoir and fill it with clean water.

Ensure the submersible pump is fully submerged.

Step 2 — Check All Connections

Moisture sensor should be firmly inserted into the soil.

Silicone tube should run from the pump outlet into the soil container.

All wires should be securely connected to the Arduino and breadboard:

Pump power via transistor/relay module

Moisture sensor signal line to analog input


Step 3 — Power the System

Connect the Arduino via USB and an external power supply for the pump (recommended 5V–9V).

3. How to Use the System

Normal Operation

Insert moisture sensor into the soil.

Power the Arduino.

The system continuously reads soil moisture.

When moisture drops below your programmed threshold:

Arduino turns ON the pump

Water flows through the silicone tube into the soil

The pump automatically stops once sufficient moisture is detected.

You do not need to manually switch the pump, it is fully automated.

4. User Tips

🌱 Adjusting Watering Sensitivity

Change the moisture threshold in your Arduino code to:

Water less often → use a lower threshold

Water more often → use a higher threshold

💧 Keep the Reservoir Filled

Check the water reservouir regularly.

Running the pump dry may damage it.

🔌 Ensure Safe Power Use

Use a proper relay or transistor driver for the pump.

Avoid powering the pump directly from the Arduino’s 5V pin.

🧼 Maintenance

Clean the moisture sensor periodically to prevent corrosion.

Ensure the tube is not clogged.

Replace pump or sensor if performance changes.

5. Troubleshooting

❌ Soil stays dry

Check pump wiring

Ensure pump is submerged

Make sure moisture threshold is set correctly

Verify the moisture sensor is inserted firmly into the soil

❌ Pump runs continuously

Moisture sensor may not be reading correctly

Soil might be too loose around the sensor

Check the sensor’s wiring and analog value

❌ No water flow

Tube may be kinked

Reservoir may be empty

Pump may be clogged


![telegram-cloud-photo-size-2-5310186544624767129-y](https://github.com/user-attachments/assets/213ddd17-471d-45b1-b860-a6955ad8bd4c)



# Project Summary:

Purpose:

The purpose of this project is to design and build an automatic irrigation system that can water plants without manual intervention. Using an Arduino, a moisture sensor, a submersible pump, and simple household materials, the system monitors soil moisture and activates watering only when needed. The goal is to create a low-cost, efficient solution for maintaining healthy plants, reducing water waste, and automating plant care.

Outcomes:

• Automated Watering: The system successfully detects soil moisture levels and activates the pump automatically when the soil becomes dry.

• Efficient Water Use: By only watering when needed, the system prevents overwatering and conserves water.

• Reliable Operation: The combination of moisture sensor and pump provides consistent and responsive irrigation based on real-time soil conditions.

• Low-Cost Design: Using common components (Arduino, bottles, tubing) results in an affordable and easy-to-build solution.

• Scalable Concept: The design can be expanded to support multiple plants or integrated into larger smart-home systems.

• Educational Value: The project demonstrates core concepts in electronics, sensors, automation, and embedded programming.
