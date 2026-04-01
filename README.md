# Gyro Based Compact Vehicle Real Time Accel Display

A compact STM32-based real-time acceleration and tilt display device designed for vehicles and motion monitoring scenarios.  
It uses an onboard IMU sensor to calculate dynamic acceleration and inclination angle in real time, and presents the data through dual 4-digit seven-segment displays and a 5-level LED acceleration indicator.

## Real Device
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/display_demo1.jpg" alt="display_demo1" width="50%">
</div>
<div align="center">
<img src="https://github.com/excezon/gyro-based-compact-vehicle-real-time-accel-display/raw/main/assets/display_demo2.jpg" alt="display_demo2" width="50%">
</div>

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

## Project Value
This project highlights several notable aspects of embedded system design, including:
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
