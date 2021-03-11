---
description: Photos and description of the inside of a typical Raspberry Pi SensorGnome
---

# Appendix B: Overview of Raspberry Pi SG Hardware

The numbering of the USB ports is very important when attaching antennas since this information is recording along with detection data and can be used to determine the direction and time of approach or departure of a tagged animal.

![Ethernet port on the left, and the 4 USB ports of a Raspberry Pi](.gitbook/assets/rpiports.jpg)

The MicroSD card slot is on the opposite side as the USB and Ethernet Ports. The card is inserted with the contacts facing up, and there is no click or other indicator when the card is inserted. On some cases the the MicroSD is so deeply recessed that it cannot be removed without tweezers.

![MicroSD card slot on a Raspberry Pi](.gitbook/assets/rpisdslot.jpg)

Power is supplied to a RPi through the Micro USB port. This port only supplies power and is not used to communicate with a computer.

![Micro USB port on a Raspberry Pi](.gitbook/assets/rpi5v.jpg)

![The primary components inside a typical Raspberry Pi SensorGnome](.gitbook/assets/sginternal.jpg)

1. The Raspberry Pi. The colour of the RPi case may vary between SG’s but they will also be roughly the same size
2. Two FunCUBE Dongles. A Raspberry Pi SG can accommodate up to 4 dongles plugged directly into the RPi. In order to accommodate additional antennas, a USB hub would be required. The cables from the antennas will plug into the free end of the dongles.
3. This is the inside view of the button used to activate the WiFi hotspot.
4. GPS antenna. When deployed in the field, this end of the antenna would be outside the SG case, and attached to something that had a clear view of the sky. The other is attached to the Raspberry Pi by way of the gold-coloured “SMA” port on the top right corner.
5. Voltage converter. If powered by a solar panel and battery, as this SG is, the power coming in will be 12V. However the RPi only requires 5V, so a voltage converter is used to downgrade the current to the acceptable level. If powered directly by AC power, the wall adapter itself should output 5V, eliminating the need for a voltage converter.

