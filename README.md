USB Audio DAC (CM108B + MAX97220)
Overview
<img width="980" height="453" alt="image" src="https://github.com/user-attachments/assets/cc989d47-52d0-4228-a59a-6e8fcd2c418e" />

This project is a compact USB audio DAC with a headphone amplifier.
The board converts USB audio from a computer into an analog stereo signal and drives headphones through a 3.5 mm audio jack.

The design is based on the CM108B USB audio controller and the MAX97220 headphone amplifier.

The board is intended as a learning project for PCB design and mixed-signal audio layouts.


Features

USB Audio Class compatible DAC
Stereo headphone output
Integrated headphone amplifier
USB Type-C input
Compact PCB layout (42 × 21 mm)
ESD protection on USB data lines
Separate analog and digital grounds


Hardware Architecture

The board consists of four main blocks:

1. USB Interface
The board uses a USB Type-C connector operating in USB 2.0 device mode.
Key components:
USB-C connector
5.1k pull-down resistor on CC pin
ESD protection (USBLC6)
Series resistors on D+ and D−
VBUS is used as the main power source.

2. Power Supply
Power is provided from the USB VBUS line (5 V).
An AMS1117-3.3 LDO regulator generates the 3.3 V rail used by:
CM108B
MAX97220
Decoupling capacitors are placed on both input and output of the regulator.

3. USB Audio Codec
The CM108B handles USB audio communication and converts digital audio into analog signals.
Main functions:
USB audio interface
Stereo DAC
Line level outputs (LEFT / RIGHT)
USB data lines include:
ESD protection
22 Ω series resistors
   
4. Headphone Amplifier
The analog output of the CM108B feeds the MAX97220 headphone amplifier.
The amplifier provides:
Low distortion
Sufficient current to drive headphones
Stereo output
The amplifier output is routed to a 3.5 mm TRS headphone jack.

Audio Path
USB → CM108B DAC → MAX97220 amplifier → 3.5 mm headphone jack

PCB Design Notes
Important layout considerations used in this design:
Analog and digital grounds are separated (AGND / DGND)
Grounds are connected at a single point
USB differential pair routed together
ESD protection placed close to USB connector
Decoupling capacitors placed near IC power pins
Bottom PCB layer is recommended to be a solid ground plane.

Main Components
Component	Description
CM108B	USB audio controller
MAX97220	Headphone amplifier
AMS1117-3.3	3.3 V LDO regulator
USBLC6	USB ESD protection
GT-USB-8016A	USB Type-C connector
PJ-320A	3.5 mm audio jack
Intended Use

This project is primarily intended for:
learning PCB layout
practicing mixed signal design
experimenting with USB audio devices

Status
Prototype design.
Not yet hardware tested.

License
Open hardware project.
