# Autopilot Board

## TOC
1. [Proposal](#proposal)
1. [Plan](#plan)
    1. [Design via EAGLE](#design-via-eagle)
    2. [Fabricate Boards](#fabricate-boards)
    3. [Source Components](#source-components)
    4. [Assemble Boards](#assemble-boards)
2. [Design Requirements](#design-requirements)

## Proposal

An autopilot is a control board for a robot, such as a quadrotor or a car, that
blends integration of the servo control, the sensors, and a coprocessor to
handle control calculations for the robot.

Some Examples:
- [Navio 2](https://emlid.com/navio/)
- [PXFMini](https://erlerobotics.com/blog/product/pxfmini/)
- [Erle-Brain 3](https://erlerobotics.com/blog/product/erle-brain-3/)

Commercial boards are expensive and often inaccessible to new users and students. One major autopilot producer's boards linked above have been on backorder for over a year.

Our proposal is to build an autopilot clone for personal DIY projects and for educational use. The board should function with commonly-available boards as a hat for Raspberry Pi, ODROID, etc.

## Plan

### Design via EAGLE

To begin, we will plan out the board layout and select components. The board will be designed using Autodesk [EAGLE (Free Student Download)](http://www.autodesk.com/education/free-software/eagle).

### Fabricate Boards

Our boards will be fabricated as cheaply as possible, and so we are looking into two low-cost PCB fabrication companies in China who offer 10 boards for $10, [Elecrow](https://www.elecrow.com/services/pcb-prototyping/10pcs-2-layer-pcb.html) and [SeeedStudio](https://www.seeedstudio.com/fusion_pcb.html).

### Source Components

We will attempt to source our components from as few sources as possible to reduce cost, and will likely source our parts from [DigiKey](http://www.digikey.com). Component cost is the highest incumbent cost of the project, and we will hope to keep this down as much as possible without sacrificing functionality.

### Assemble Boards

In order to keep assembly costs low, we will solder the components to the boards ourselves using reflow solder techniques. Board assembly in the United States runs up to $100/board, and in China, assembly is often priced per component, and often doubles the cost of the components.

If we assemble the boards ourselves, we can cut the cost down dramatically. Assembling the boards requires the use of some DIY soldering techniques, such as the use of a reflow skillet and solder paste application by hand.

## Design Requirements

We hope to use reliable, high-quality components, and implement all of the main features of a traditional autopilot, including an IMU, Coprocessor, Barometer, PWM servo-control, peripheral connectivity (I2C, UART, etc.), power regulation, etc.

### Core Features

- Coprocessor for FPU and control calculations (ARM Cortex-M4)
- IMU for movement tracking (MPU9250)
- Servo/motor control using PWM.
- Compatible with Raspberry Pi Zero & 3.

### Secondary Features

- Barometer/Altitude sensor (MS5611)
- GPS/GNSS module (U-blox M8N)
- Hat EEPROM
- Precision ADC
