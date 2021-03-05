# Appendix: Overview of BeagleBone SG Hardware

The primary ports of a BeagleBone

1. Mini USB port. This is the main port used to connect a BB to your computer. It also supplies enough power to power the BB on its own if needed
2. Ethernet Port. Most often used for automatic syncing of detection data to the Motus server.
3. 5V barrel jack port. This is where the primary power supply is plugged in when deployed in the field

Secondary ports of a BeagleBone

1. USB port. FunCUBE and other dongles are plugged in here. Because there is only one such port on a BB, it will almost always be used to connect a USB hub. This port is _not_ used for communication between the computer BB.
2. MicroSD card slot. In the BB the card is inserted with the contacts facing down, and there is a slight click when properly inserted.

The primary components inside a typical BeagleBone SensorGnome

1. BeagleBone mini computer. The colour of the case may vary but it will always be roughly the same size.
2. 3 FunCUBE dongles. The antenna cables would be attached to the loose ends. Note that the antennas must be plugged into a USB hub as the BB only has one standard USB port.
3. This USB cable powers the GPS. This particular BB SG lacks an integrated “GPS hat” and uses the original USB GPS. The USB GPSs are prone to lapses in timekeeping, which can result in irretrievable detection data so in most cases they have been replaced with GPS hats, which have battery backup
4. USB hub. The power cable is not pictured. The ports are numbered 1-7 from top to bottom in this picture.
5. Voltage converter. If powered by a solar panel and battery, as this SG is, the power coming in will be 12V. However the RPi only requires 5V, so a voltage converter is used to downgrade the current to the acceptable level. If powered directly by AC power, the wall adapter itself should output 5V, eliminating the need for a voltage converter.

The top of the USB hub in this view includes the DV barrel jack power supply, as well as the USB port where the hub would be connected to the BeagleBone. Along the bottom the antenna USB ports are numbered from 1-7. The top

