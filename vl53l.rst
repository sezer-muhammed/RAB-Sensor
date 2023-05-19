===================
VL53L5CX ToF Sensor
===================

Overview
========

The VL53L5CX is a state-of-the-art Time-of-Flight (ToF), multizone ranging sensor that enhances the ST FlightSense product family. It's housed in a miniature reflowable package and integrates a Single Photon Avalanche Diode (SPAD) array, physical infrared filters, and diffractive optical elements (DOE) to achieve superior ranging performance in various ambient lighting conditions with a variety of cover glass materials.

The sensor utilizes a DOE above the vertical cavity surface emitting laser (VCSEL) to project a square Field of View (FoV) onto the scene. The reflected light is then focused by the receiver lens onto a SPAD array. Unlike conventional IR sensors, the VL53L5CX uses ST's latest generation, direct ToF technology, enabling it to measure absolute distance regardless of target color and reflectance.

It provides accurate ranging up to 400 cm and operates at fast speeds (60 Hz), making it the fastest multizone, miniature ToF sensor on the market. Multizone distance measurements are possible up to 8x8 zones with a broad 65° diagonal FoV, which can be reduced by software.

Thanks to ST's patented Histogram algorithms, the VL53L5CX can detect different objects within the FoV. The Histogram also offers immunity to cover glass crosstalk beyond 60 cm.


Detection Volume and Exclusion Zone
===================================

The VL53L5CX sensor has specific detection volumes and collector exclusion zones based on different angles:

- Detection volume: 45°, 45°, 65°
- Collector exclusion zone: 55.5°, 61°, 82°


Key Features
============

The VL53L5CX is a fast and accurate multizone distance ranging sensor with the following features:

- Multizone ranging output with either 4x4 or 8x8 separate zones
- Autonomous low-power mode with interrupt programmable threshold to wake up the host
- Ranging up to 400 cm
- Multitarget detection and distance measurement in each zone
- 60 Hz frame rate capability
- Histogram processing, and algorithmic compensation minimizes or removes impact of cover glass crosstalk
- Motion indicator for each zone to show if targets have moved and how they have moved
- Fully integrated miniature module with wide field of view (FoV)
  - Emitter: 940 nm invisible light vertical cavity surface emitting laser (VCSEL) and integrated analog driver
  - 65° diagonal square FoV using diffractive optical elements (DOE) on both transmitter and receiver
  - Receiving array of single photon avalanche diodes (SPADs)
  - Low-power microcontroller running Firmware
  - Size: 6.4 x 3.0 x 1.5 mm
- Easy integration
  - Single reflowable component
  - Flexible power supply options, single 3.3 V or 2.8 V operation, or combination of either 3.3 V or 2.8 V AVDD with 1.8 V IOVDD
  - Compatible with a wide range of cover glass materials


Applications
============

The VL53L5CX ToF sensor is well-suited for a wide range of applications, including:

- Scene understanding: Multizone and multi-object distance detection enables 3D room mapping and obstacle detection for robotics applications
- Wide FoV and multizone scanning allows content management (load in trucks, tanks, waste bins)
- Gesture recognition
- Liquid level control
- Keystone correction for video projectors
- Laser assisted autofocus (LAF): Enhances the camera AF system speed and robustness especially in difficult low light or low contrast scenes
- Augmented reality/virtual reality (AR/VR) enhancement: Dual camera stereoscopy and 3D depth assistance thanks to multizone distance measurement
- Smart buildings and smart lighting: User detection to wake up devices
- IoT: User and object detection
- Video focus tracking: 60 Hz ranging allows optimization of continuous focus algorithms


Specifications
==============

.. csv-table:: VL53L5CX Specifications
   :header: "Attribute", "Value"
   :widths: 20, 20

   "Package", "Optical LGA16"
   "Size", "0.5″ x 0.7″ x 0.085″ (13 mm x 18 mm x 2 mm)"
   "Ranging", "20 mm to 4000 mm per zone"
   "Operating Voltage (IOVDD)", "2.8 V to 5.5 V"
   "Operating Temperature", -30 to 85°C"
   "Infrared Emitter", "940 nm invisible Class 1 VCSEL (vertical cavity surface-emitting laser)"
   "I2C Interface", "400 kHz (I²C fast mode standard), Address: 0101001b on power-up"
   "Operating Mode", "Continuous"


More Information
================

For more details about the VL53L5CX ToF sensor, refer to the official datasheet: https://www.st.com/resource/en/datasheet/vl53l5cx.pdf. 

Or pololu version with more examples: https://www.pololu.com/product/3417

Complete datasheet: https://www.pololu.com/file/0J1878/vl53l5cx.pdf

Arduino Library with examples: https://github.com/sparkfun/SparkFun_VL53L5CX_Arduino_Library

Using the VL53L5CX with I²C
==============================

The VL53L5CX is a carrier board for ST’s VL53L5CX laser-ranging sensor, offering fast and accurate ranging up to 4 m through a digital I²C interface. 

Connections
------------

At least four connections are necessary to use the VL53L5CX board: VIN, GND, SCL, and SDA. 

- **VIN**: This should be connected to a 2.8 V to 5.5 V source. 
- **GND**: This should be connected to 0 volts. 

The I²C pins, SCL and SDA, are connected to built-in level-shifters that make them safe to use at voltages over 3.3 V. They should be connected to an I²C bus operating at the same logic level as VIN. 

Pinout
-------

- **VIN**: This is the main 2.8 V to 5.5 V power supply connection. The SCL and SDA level shifters pull the I²C lines high to this level. 
- **SDA**: Level-shifted I²C data line: HIGH is VIN, LOW is 0 V  
- **SCL**: Level-shifted I²C clock line: HIGH is VIN, LOW is 0 V  

I²C communication
--------------------

The VL53L5CX can be configured and its distance readings can be queried through the I²C bus. Level shifters on the I²C clock (SCL) and data (SDA) lines enable I²C communication with microcontrollers operating at the same voltage as VIN (2.8 V to 5.5 V). 

The sensor’s 7-bit target address defaults to 0101001b on power-up. It can be changed to another value by writing one of the device configuration registers, but the new address only applies until the sensor is reset or powered off. 

The I²C interface on the VL53L5CX is compliant with the I²C fast mode (400 kHz) standard. 