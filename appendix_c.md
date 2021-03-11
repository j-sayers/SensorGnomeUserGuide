---
description: Photos and description of the inside of a typical BeagleBone SensorGnome
---

# Appendix C: Overview of BeagleBone SG Hardware

![Primary ports of BeagleBone SG](.gitbook/assets/bbports%20%281%29.jpg)

**a\)** Mini USB port. This is the main port used to connect a BB to your computer. It also supplies enough power to power the BB on its own if needed

**b\)** Ethernet Port. Most often used for automatic syncing of detection data to the Motus server.

**c\)** 5V barrel jack port. This is where the primary power supply is plugged in when deployed in the field

![Secondary ports of a BeagleBone](.gitbook/assets/bbports2%20%281%29.jpg)

**a\)** Standard USB port. Typically the USB Hub will be attached here as the BB only has one standard USB port. FUNcubes and other dongles are then plugged in to the USB hub. This port is not used for communication between the computer and BB.

**b\)** MicroSD card slot. In the BB the card is inserted with the contacts facing down, and there is a slight click when properly inserted.

![](.gitbook/assets/bbsg.jpg)

**a\)** BeagleBone mini computer. The colour of the case may vary but it will always be roughly the same size.

**b\)** GPS antenna. This BB has a "GPS hat" attached to the BeagleBone itself, and only requires an external antenna. Many BB last the integrated GPS and require a USB GPS, which is plugged into the USB hub

**c\)** FUNcube dongles plugged into ports 1 and 2 of the USB hub. The antenna cables would be attached to the loose ends. Note that the antennas must be plugged into a USB hub as the BB only has one standard USB port.

**d\)** USB hub. The USB hub is supplied with power by via a splitter coming from the main power source, with the other end supplying the BeagleBone. It is attached to the BB's only standard USB port.

**e\)** Voltage converter and cable junction. If powered by a solar panel and battery, as this SG is, the power coming in will be 12V. However the RPi only requires 5V, so a voltage converter is used to downgrade the current to the acceptable level. If powered directly by AC power, the wall adapter itself should output 5V, eliminating the need for a voltage converter.

{% hint style="warning" %}
Pay close attention to which ports on the USB hub you attach the dongles to. The port number is recorded along with the detection data and is used in determining the direction of the animals detected. The ports on the USB hub are labelled 1 through 7. If the label is missing, you can determine the numbering based on their position relative to the USB and power supply. 
{% endhint %}

![USB hub and associated cables](.gitbook/assets/usbhub.jpg)

The 7 USB ports on the hub can all be used to attach dongles to, but pay close attention to the number of each port and the antenna attached to it. The USB hub is supplied with 5V power, usually by way of a splitter \(with the other end supplying the BB with power\). It is attached to the BB with a standard [USB A &gt;  USB B cable](https://www.bhphotovideo.com/images/images2500x2500/Pearstone_USB_AB10_USB_2_0_Type_A_689978.jpg). 

