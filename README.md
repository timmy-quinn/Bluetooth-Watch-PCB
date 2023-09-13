# Bluetooth-Watch-PCB
The goal of this project was to design a PCB for a BLE watch. The watch will be used as a low-power means of telling the time, receiving phone alerts, and counting steps. 

### Time display
The watch uses a 24 LED display which is based on this [project](https://www.youtube.com/watch?v=nHZllsSoZp4). This design however uses 24 LEDs instead of just 12. This is done so that the minute and hour can be displayed simultaneously. The outer ring indicates the minute (rounded to the nearest five) and the inner ring indicates the hour. The outer and inner rings will each de different colors. Additionally, my watch will use the accelerometer to determine when the wearer has the watch in viewing position before turning on the LEDs in order to save power. The LEDs will all flash when receiving an alert. 

![PCB Image]([https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/3b79429ff4e6e844e353ab953f97ed3d51d7d187/watch_screenshot.png](https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/main/3dPCBView.png))

### Additional Hardware considerations
For the MCU I selected an NRF52 because of its low power consumption and because it supports BLE. To enable Bluetooth connectivity the watch uses a compact 2.45 GHz microstrip antenna which fits snuggly on the edges of the PCB, with a 50 ohm impedance matching network from the [NRF52 product specifications](https://github.com/timmy-quinn/Bluetooth-Watch-PCB/blob/3b79429ff4e6e844e353ab953f97ed3d51d7d187/reference%20documents/nRF52832_PS_v1.4.pdf).





