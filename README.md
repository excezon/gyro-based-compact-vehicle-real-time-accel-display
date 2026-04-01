# Gyro Based Compact Vehicle Real Time Accel Display

A compact STM32-based real-time acceleration and tilt display device designed for vehicles and motion monitoring scenarios.  
It uses an onboard IMU sensor to calculate dynamic acceleration and inclination angle in real time, and presents the data through dual 4-digit seven-segment displays and a 5-level LED acceleration indicator.
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/display_demo1.jpg" alt="display_demo1" width="50%">
</div>
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/display_demo2.jpg" alt="display_demo2" width="50%">
</div>

### PCB Design
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/PCB_top_layer.png" alt="PCB_top_layer" width="50%">
</div>

### Project Overview
This project is a compact portable real-time motion display system.

It is designed to measure and visualize:
- **Current acceleration** in real time
- **Current tilt angle / inclination**
- **Acceleration intensity** through LED bar indication

At power-on, the device waits for **1 second** and samples the IMU output to calculate the average sensor baseline.  
The current device orientation is then treated as the **horizontal reference position**. At the same time, gravity compensation is applied so that the displayed acceleration is initialized to **0** in the current static state.

During operation:
- The **upper 4-digit display** shows the current real-time acceleration
- The **lower 4-digit display** shows the current tilt angle
- The **5 red LEDs on the left side** indicate acceleration magnitude:
  - higher acceleration lights more LEDs
  - when acceleration exceeds a predefined threshold, the LEDs **flash rapidly** as a warning

To improve long-term stability, when the device remains still for more than **5 seconds** and both acceleration and tilt change stay within a small threshold, the system will automatically:
- re-calibrate the current orientation as horizontal
- compensate gravity again
- reset the displayed acceleration back to 0

The device supports **dual power input**, including:
- **USB-C power**
- **Lithium battery power**

This project demonstrates embedded system design across hardware, firmware, sensor calibration, motion data processing, real-time display driving, and portable power management.

## Key Features
- Real-time **acceleration** display
- Real-time **tilt angle** display
- Dual 4-digit seven-segment visual interface
- 5-level LED acceleration intensity indicator
- Threshold-triggered fast flashing warning
- Automatic static-state re-calibration
- Power-on baseline averaging and gravity compensation
- **USB-C + battery** dual power supply
- Compact PCB design suitable for portable or in-vehicle use

## System Behavior
### Power-On Calibration
After power-up, the device:
1. waits for 1 second
2. samples and averages the gyroscope / IMU data
3. defines the current pose as the horizontal reference
4. removes gravity offset from acceleration output
5. initializes displayed acceleration to 0

### Real-Time Display
- **Top row 4-digit display:** current acceleration
- **Bottom row 4-digit display:** current tilt angle

### LED Indication Logic
- Low acceleration → fewer LEDs on
- Higher acceleration → more LEDs on
- Over-threshold acceleration → LEDs flash rapidly

### Automatic Re-Zero / Re-Leveling
When the device stays motionless and both acceleration and tilt remain within preset thresholds for more than 5 seconds, the system automatically redefines the current position as level and re-zeros the acceleration output.

## Hardware Highlights
- **STM32 microcontroller** based control system
- **IMU sensor** for motion and attitude detection
- Dual 4-digit seven-segment display modules
- 5 red LEDs for acceleration level indication
- USB-C power input
- Lithium battery power support
- Compact custom PCB

## Firmware Highlights
- Sensor sampling and averaging
- Startup baseline calibration
- Gravity compensation
- Static-state detection
- Automatic drift correction / re-zeroing
- Real-time display refresh
- LED threshold warning logic

## Hardware Preview
### PCB Design
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/PCB_top_layer.png" alt="PCB_top_layer" width="50%">
</div>

<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/PCB_bottom_layer.png" alt="PCB_bottom_layer" width="50%">
</div>

### Schematic Diagram
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/Schematic.png" alt="Schematic" width="50%">
</div>

## Real Device
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/display_image.jpg" alt="device_photo_1" width="45%">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/display_image_2.jpg" alt="device_photo_2" width="45%">
</div>

## Project Value
This project is a strong embedded portfolio piece that reflects practical engineering ability in:
- embedded hardware design
- STM32 firmware development
- IMU data processing
- calibration and compensation algorithms
- real-time digital display driving
- battery / USB dual-power system design
- complete prototype implementation from schematic to functional hardware

## Suitable Application Scenarios
- Vehicle motion monitoring
- Portable acceleration / attitude indicator
- Embedded sensing demonstration platform
- Personal embedded systems portfolio project
