# Data syncing over the Internet

The simplest method of syncing data over the internet is to plug the BB or RPi into the Internet via an Ethernet cable – if the internet is not password protected, and the software on the SG is up-to-date, this should happen automatically within minutes.

But often a WiFi network is preferred. In this case a bit of configuration is needed. The Raspberry Pi comes with a WiFi adapter already on-board. WiFi connectivity is also possible with a BeagleBone, though it requires a USB WiFi adapter.

1. Connect to the SG
2. Open FileZilla and establish an FTP connection with the SG
3. Navigate to the uboot folder
4. Right click on the `network.txt` file and select “edit”
5. Follow the instructions in the file and enter the appropriate information.
6. Ensure that the changes have been saved to the SG, then power down and reboot
7. Confirm that the SG is connected by visiting [sensorgnome.org/status](sensorgnome.org/status). This page displays a master list of SensorGnomes that are, or have recently been, connected to the Internet.

   Within a minute or so of connecting to the Internet, an SG should check in with the SensorGnome.org server. Hit `CRTL F` in the browser and then type in the receiver serial number. You should see the recently connected receiver in this list. Data syncing usually occurs an hour after initial connection.

Connection status deployed on SensorGnome.org/status

_Note: Activating the WiFi hotspot will temporarily disable the connection to the Internet. One the WiFi hotspot turns off, the connection to the Internet will be re-established._

