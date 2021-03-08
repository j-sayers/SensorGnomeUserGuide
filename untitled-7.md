# Data syncing over the Internet

Configuring your SensorGnome to sync detection data automatically result in more up-to-date data, fewer trips to visit a station, and more timely identification \(and resolution\) of any issues the receiver. Wherever possible, SG's should be connected to the Internet.

## Option 1: Wired internet over Ethernet

The simplest method of syncing data over the internet is to plug the BB or RPi into the Internet via an Ethernet cable. If the internet is not password protected, and the software on the SG is up-to-date, this should happen automatically within minutes.

## Option 2: Wi-Fi 

Connecting over a Wi-Fi network is also an option. In this case a bit of configuration is needed. The Raspberry Pi comes with a Wi-Fi adapter already on-board. Wi-Fi connectivity is also possible with a BeagleBone, though it requires a USB Wi-Fi adapter. The BeagleBone software is configured to work with the [TP-Link TL-WN725N Wi-Fi adapter](https://www.tp-link.com/us/home-networking/usb-adapter/tl-wn725n/). This is an affordable and reliable Wi-Fi adapter that is available from multiple retailers.

{% hint style="info" %}
The Wi-Fi network you wish to use must be configured with WPA2 security. This is the standard on most Wi-Fi networks already. An SG will _not_ connect to a Wi-Fi network that has no password.
{% endhint %}

1. Connect to the SG
2. Open FileZilla and establish an FTP connection with the SG
3. Navigate to the uboot folder
4. Right click on the `network.txt` file and select “edit”
5. Follow the instructions in the file and enter the appropriate information.
6. Ensure that the changes have been saved to the SG, then power down and reboot
7. Confirm that the SG is connected by visiting [sensorgnome.org/status](sensorgnome.org/status). This page displays a master list of SensorGnomes that are, or have recently been, connected to the Internet.

   Within a minute or so of connecting to the Internet, an SG should check in with the SensorGnome.org server. Hit `CRTL F` in the browser and then type in the receiver serial number. You should see the recently connected receiver in this list. Data syncing usually occurs an hour after initial connection.

_Note: Activating the WiFi hotspot will temporarily disable the connection to the Internet. One the WiFi hotspot turns off, the connection to the Internet will be re-established._

## Checking sync status on sensorgnome.org

Connection status deployed on SensorGnome.org/status

\_\_

