# Connecting to your SensorGnome

In order to copy detection data from the SG, to check the SG’s live status in the Web Interface, or to apply a software patch, you must establish a connection between the SensorGnome and your computer. The actual method used will depend on whether you are using a RPi or BB SG, but the end result is similar in each case. Click on the appropriate tab below to switch between instructions for Raspberry Pi and BeagleBone SGs.

## Connection steps for Raspberry Pi & BeagleBone SensorGnomes

{% tabs %}
{% tab title="Raspberry Pi" %}
### Raspberry Pi SensorGnome

There are two methods available for connecting to a RPi SG: Wi-Fi Hotspot or Ethernet cable. The Wi-Fi hotspot can be more convenient, but not every RPi SG is equipped with this functionality. Ethernet cable should work in every case.

{% hint style="warning" %}
Make sure you have iTunes installed first. iTunes includes a networking tool called Bonjour which is required for this process. If you don't want iTunes you can download Bonjour on its own [here](https://downloads.digitaltrends.com/bonjour/windows). This is not required for Mac users as Bonjour comes preinstalled.
{% endhint %}

#### Option 1: Wi-Fi Hotspot

The RPi that powers the SG is capable of producing a local Wi-Fi hotspot that a computer or smartphone can connect to. This doesn’t connect to the internet, but simply forms a network connection between the SG and your computer.

An RPi SG with the ability to create a hotspot will have a silver button somewhere on the outside of the SensorGnome case. This button is used to activate the hotspot. If there is no button then it will not be capable of creating a hotspot and you will have to connect with Option 2: Ethernet Cable.

![The Wi-Fi Hotspot activation button](.gitbook/assets/wifibutton.png)

The Wi-Fi hotspot is convenient because, once a computer (or smartphone) has connected once to that particular RPi SG, it will not require any additional configuration and all further interactions with that SG can be performed by pressing the Wi-Fi button and leaving the SG case itself closed.

The disadvantage is that activating the Wi-Fi hotspot via the button can be finicky. Sometimes it takes several tries, and sometimes it doesn’t work at all.

**1)** Activate the Wi-Fi hotspot by double pressing the Wi-Fi button on the SG case. If properly activated the button will commence a slow on/off blinking pattern (the actual pattern of the blinking may vary).

**2)** The Wi-Fi hotspot should soon appear in the list of available Wi-Fi networks to connect to. The name of the Wi-Fi Network and the password will be the same as the serial number of the RPi SG (e.g. SG-A123RPI43D3).

* It can take up to a minute for the Wi-Fi network to appear.
* The LED light in the button is usually bright enough to view in sunlight, but occasionally it is very faint and difficult to see
* The timing of the double press can be finicky and difficult to activate. If it doesn’t work, try it again.

**3)** Connect to the new Wi-Fi network. The password is the same as the network name, which is the same as the serial number of the RPi SG. This is just a local network so there won’t be any internet once connected.

![The network name and the password are both the same as the SG serial number](.gitbook/assets/wifi.png)

**4)** After waiting 30-60 seconds, confirm that the connection is established by opening the Web Interface

* Open a web browser (Firefox or Chrome)
* Navigate to `http://192.168.7.2`
* You should now see the SensorGnome Web Interface

{% hint style="info" %}
The WiFi hotspot should deactivate automatically after about 30 minutes.&#x20;
{% endhint %}

#### Option 2: Ethernet Cable

An Ethernet cable is usually the most reliable way of connecting to a RPi SG, and doesn’t depend on having a Wi-Fi hotspot activation button. No configuration is needed on the RPi. However some configuration may be required on your computer.

![Ethernet cable](.gitbook/assets/ethernet.jpg)

If you use a Windows computer, ensure that iTunes is installed. Installing iTunes also installs a networking tool called Bonjour that the SG relies on to establish the connection. If you don’t want to install iTunes, you can install [Bonjour by itself directly from Apple](https://support.apple.com/kb/DL999?locale=en\_CA). If you use a Mac computer, Bonjour should already be installed.

**1)** Power on the RPi

**2)** Connect one end of the Ethernet cable to the Ethernet port on the Raspberry Pi and the other end to your computer

* Many newer computers do not have an Ethernet port. If yours lacks an Ethernet port, you can use an “Ethernet to USB adapter” to connect to one of your computer’s USB ports.

**3)** After waiting 30-60 seconds, confirm that the connection is established by accessing the Web Interface

* Open a web browser (Firefox or Chrome)
* Navigate to `http://sgpi.local`
* You should now see the SensorGnome Web Interface
{% endtab %}

{% tab title="BeagleBone" %}
### BeagleBone SensorGnome

USB cable is usually the preferred method of connecting to a BeagleBone SG. The USB cable used is a Mini USB to USB cable. These aren’t as commonly found in day-to-day usage as they used to be but can still be found easily and for affordable prices online. Purchase a few so that you have a couple extras available.

{% hint style="warning" %}
Before connecting to a BeagleBone SG for the first time, it is likely you’ll need to install drivers. Instructions on how to do this can be found in the [Appendix](appendix/bbdrivers.md).
{% endhint %}

![Mini USB to Standard USB cable](.gitbook/assets/usbab.jpg)

**1)** Connect the Mini USB end to the BeagleBone. The port is found on the same side as the 5V barrel jack and Ethernet port.

* The USB connection will also power the BB by itself if needed. However if a primary power supply is already plugged in to the barrel jack, you can simply plug in the USB cable while the BeagleBone is powered on.

![The Mini USB port used to connect to a BeagleBone](.gitbook/assets/bbusb.png)

**2)** After 30 to 60 seconds, confirm that the connection is established by accessing the Web Interface

* Open a web browser (Firefox or Chrome)
* Navigate to `http://192.168.7.2`
* You should now see the SensorGnome Web Interface
{% endtab %}
{% endtabs %}

## Troubleshooting the Connection

An inability to access the Web Interface may indicate issues with your SensorGnome. However there are a number of other potential causes. Here are a few suggestions as part of the troubleshooting process if you are running into issues.

* If your SensorGnome is off-grid or powered with a non-standard power supply, see [Underpowered SensorGnomes](appendix/underpowered-sensorgnomes.md).
* Check your power supply. Both the [RPi ](appendix/anatomy.md#rpi-lights)and [BB ](appendix/anatomy.md#bb-lights)have diagnostic LED lights to make visual confirmation of power supply easier.&#x20;
* Sometimes it takes a while for the connection to the SG to be established, especially for the RPi Ethernet connection which may take _up to a minute_ to establish. If you do not see the Web Interface, wait several seconds before trying again.
* Ensure you are using the correct URL for that SensorGnome and connection method
* If you try to access the Web Interface before the connection to the SG has been fully established, some browsers will automatically replace the `http://` prefix with `https://` or  add `www.`. Correct the URL in the address bar is  before trying again.
* Try a different connection method if you have the option
* Make sure the cables you are using are connected properly. Try different cables if you have them.
* Try a different USB port if applicable
* Toggle the WiFi on your computer on/off if you are trying to connect to a RPi hotspot
* Reboot and restart both the computer and SG
* Try a different computer if you have one available. Preferably one that you've confirmed can actually connect to this type of SG
* Try a different internet browser
* Many newer Windows computers repeatedly reset BeagleBone driver settings. You can fix that following the instructions here: [restoring-beaglebone-drivers-on-windows.md](appendix/restoring-beaglebone-drivers-on-windows.md "mention")
* Use [Bonjour Browser ](appendix/bonjourbrowser.md)to get the IP address of a connected Raspberry Pi SG&#x20;
* Re-image the SG (if it's a BeagleBone) or try a clean software version (if it's a Raspberry Pi). Instructions can be found in the [updating SG software section](updating.md).
* If you just need to download data there a few other methods of getting this as a temporary solution (see [downloading detection data section](downloading.md))
* If you still cannot access the Web Interface, you will not be able to confirm that the SG is running properly. Don’t leave an SG deployed in the field in this condition unless you have no other option.&#x20;
  * For BeagleBone SG's you can make a "rescue image" and run the SG directly from the software card. More details on making a rescue image can be found [here](appendix/rescue.md#running-a-bb-sg-from-the-rescue-image).
