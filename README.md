# Bluetooth-Watch-PCB
The goal of this project was to design a PCB for a BLE watch. This PCB will be a platform to enable me to experiment with different IoT applications. The accelerometer will be used to determine when to display the time, so that the LEDs are only on when the user has it in an appropriate position. The accelerometer may also be used to enable gesture-controlled functions. In particular I would like to experiment with using RSSI localization as a method of tracking indoors, to automate functions like lights turning on and off. 

### Time display
The watch uses a 24 LED display which is based on this [project](https://www.youtube.com/watch?v=nHZllsSoZp4). This design however uses 24 LEDs instead of just 12. This is done so that the minute and hour can be displayed simultaneously. The outer ring indicates the minute (rounded to the nearest five) and the inner ring indicates the hour. The outer and inner rings will each de different colors. Additionally, my watch will use the accelerometer to determine when the wearer has the watch in viewing position before turning on the LEDs in order to save power. The LEDs will all flash simultaneously when receiving an alert. Or rather, it will appear that all the LEDs are flashing simultaneously. The LEDs will be rapidly turned on and off, and persistance of vision will create the appearance that the LEDs are flashing. 

![PCB Image](https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/main/3dPCBView.png)

### Additional Hardware considerations
For the MCU I selected an NRF52 because of its low power consumption and because it supports BLE. Specifically, I selected the NRF52832-QFAA, which has a 2.4 GHz transceiver, an ARM Cortex M4 32-bit processor, a flexible power management system (with LDO or DC/DC regulator) and has 64 kB of RAM and 512 kB of Flash memory.

To enable Bluetooth connectivity the watch uses a compact 2.45 GHz microstrip antenna placed on the edge of the PCB, with a 50 ohm impedance matching network from the [NRF52 product specifications](https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/3b79429ff4e6e844e353ab953f97ed3d51d7d187/reference%20documents/nRF52832_PS_v1.4.pdf). There are multiple ground pores and volid via stitching around them, with additional via shielding around the antenna impedance matching network. 

### Circuit Diagram

![Circuit Diagram](https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/main/Full_Circuit_Diagram.png)

### LED Multiplexing Matrix

At first I considered Charlieplexing the LEDs to save GPIO pins, but I realized that I had enough pins available, and that Charlieplexing would require more resistors. So I went with this simple system. In the PCB the LEDs which share the same sink are all daisy-chained together, to enable the 

![LED Matrix](https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/main/LED_Multiplexing_Diagram.png)







