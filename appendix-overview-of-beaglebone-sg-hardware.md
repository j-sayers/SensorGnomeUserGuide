---
description: Photos and description of the inside of a typical BeagleBone SensorGnome
---

# Appendix: Overview of BeagleBone SG Hardware

![Primary ports of BeagleBone SG](.gitbook/assets/bbports%20%281%29.jpg)

a\) Mini USB port. This is the main port used to connect a BB to your computer. It also supplies enough power to power the BB on its own if needed

b\) Ethernet Port. Most often used for automatic syncing of detection data to the Motus server.

c\) 5V barrel jack port. This is where the primary power supply is plugged in when deployed in the field

![Secondary ports of a BeagleBone](.gitbook/assets/bbports2%20%281%29.jpg)

1. Standard USB port. Typically the USB Hub will be attached here as the BB only has one standard USB port. FUNcubes and other dongles are then plugged in to the USB hub. This port is not used for communication between the computer and BB.
2. MicroSD card slot. In the BB the card is inserted with the contacts facing down, and there is a slight click when properly inserted.

![The primary components inside a typical BeagleBone SensorGnome](.gitbook/assets/bbsginternal%20%281%29.jpg)

1. BeagleBone mini computer. The colour of the case may vary but it will always be roughly the same size.
2. FUNcube dongles. The antenna cables would be attached to the loose ends. Note that the antennas must be plugged into a USB hub as the BB only has one standard USB port.
3. USB hub. The power cable is not pictured, but would be attached on the left hand side. The ports are numbered 1-7 from top to bottom in this picture.
4. This USB cable powers the GPS. This particular BB SG lacks an integrated “GPS hat” and uses the original USB GPS. The USB GPSs are prone to lapses in timekeeping, which can result in irretrievable data loss so in most cases they have been replaced with GPS hats, which have battery backup
5. Voltage converter. If powered by a solar panel and battery, as this SG is, the power coming in will be 12V. However the RPi only requires 5V, so a voltage converter is used to downgrade the current to the acceptable level. If powered directly by AC power, the wall adapter itself should output 5V, eliminating the need for a voltage converter.

![USB hub](.gitbook/assets/usbhub.jpg)

The top of the USB hub in this view includes the DV barrel jack power supply, as well as the USB port where the hub would be connected to the BeagleBone. Along the bottom the antenna USB ports are numbered from 1-7. 

