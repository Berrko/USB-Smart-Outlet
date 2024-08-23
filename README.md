# USB-smart-outlet
## Usage: 

This project aims to control multiple relays via a USB connection to a PC. The system consists of a relay board housed in an enclosure with 4 sockets, a microcontroller (µC) system such as Arduino or Raspberry PI for USB communication, and a PC application for command-based relay control. The goal is to minimize handling of mains voltage by using a pre-assembled 230V relay board with digital inputs.

## Required components 
- Arduino UNO (or equivalent)
- 4-Channel Relay Module
- External Power Supply Unit (PSU) (e.g., 12V 1.25A)
- USB-TTL Adapter (e.g., FTDI adapter)
- 4x Sockets
- 4x Push Buttons with integrated LED´s 
- Connecting Wires (e.g., core lines)
- PCB Board
- Industrial housing
- ferrules for the core lines
 
The housing is 300mm long, 230mm wide and 85mm tall and spaceious enough to fit all components.

## Circuit
*Four power outlets will be used instead the lamps. The lamps shall represent a consumer.*

![grafik](https://media.github.boschdevcloud.com/user/51273/files/5ccb5c17-886d-4cda-825a-0ede6630e121)
*https://www.tinkercad.com/things/baAgEsdqXXk-usb-smartstecker*

## Software Setup
- Visual Studio Code
- Arduino CLI
- Python 3.x with `pyserial` library

## Hardware Setup

1. Install the outlets and relay board inside the housing.
2. Connect the relays to the outlets and the relay board to the microcontroller.
3. Ensure safe wiring, especially when dealing with high voltage


# Pinout Overview
## Arduino UNO

   - Vin: Connected to the positive output of the PSU (e.g., 12V).
   - GND: Connected to the ground of the PSU and to the USB-TTL adapter GND.
   - Digital Pin 2: Connected to Relay 1 IN1.
   - Digital Pin 3: Connected to Relay 2 IN2.
   - Digital Pin 4: Connected to Relay 3 IN3.
   - Digital Pin 5: Connected to Relay 4 IN4.
   - Digital Pin 6: Connected to Push Button 1.
   - Digital Pin 7: Connected to Push Button 2.
   - Digital Pin 8: Connected to Push Button 3.
   - Digital Pin 9: Connected to Push Button 4.
   - RX Pin: Connected to TX of the USB-TTL adapter.
   - TX Pin: Connected to RX of the USB-TTL adapter.

## Relay Module

   - VCC: Connected to the 5V pin of the Arduino.
   - GND: Connected to the GND pin of the Arduino.
   - IN1: Connected to Digital Pin 2 of the Arduino.
   - IN2: Connected to Digital Pin 3 of the Arduino.
   - IN3: Connected to Digital Pin 4 of the Arduino.
   - IN4: Connected to Digital Pin 5 of the Arduino.
   - COM (Common): Connected to the live wire of the sockets.
   - NO (Normally Open): Connected to one terminal of the sockets.

## Push Buttons

   - One Terminal: Connected to GND.
   - Other Terminal: Connected to respective Arduino digital pins (10, 11, 12, 13) through a 220Ω pull-up resistor (if necessary).
   - C Pin: Connected to GND
   - Normally Open Pin: Connected to respective Arduino digital pins (6, 7, 8, 9)

## USB-TTL Adapter

   - TX: Connected to the RX pin of the Arduino.
   - RX: Connected to the TX pin of the Arduino.
   - GND: Connected to the GND pin of the Arduino.

## External Power Supply Unit (PSU)

   - +V (Positive): Connected to the Vin pin of the Arduino.
   - -V (Negative): Connected to the GND pin of the Arduino.
   - AC Pins: Connected with 5V and GND pins on the Arduino power supply
   ![grafik](https://media.github.boschdevcloud.com/user/51273/files/95bb61d7-91c0-4c02-86a4-506ad8eae004)



## Last notes

- Ensure that all connections are secure and that no wires are shorting.
- The PSU should be connected to a stable power source with sufficient current capacity to avoid voltage drops.
- Measure the voltage on the PSU. It can be above 12V, which is more than required for the Vin Pin. 
- Test the circuit in a safe environment before using it in a live setting with AC mains power. 
