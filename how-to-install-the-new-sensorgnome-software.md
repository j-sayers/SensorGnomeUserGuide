# How to install the new SensorGnome software

## Requirements

* MicroSD card with _at least_ 16 GB (we recommend 32 GB, but more is also fine).
* A computer with Windows/Mac OS/Linux.
* MicroSD card adapter and an SD card reader (most MicroSD cards come with an adapter).
* The latest SensorGnome software release (as of 2023-08-12 this is [ https://sensorgnome.s3.amazonaws.com/images/pimod/sg-armv7-rpi-bullseye-testing-2023-341.zip](https://sensorgnome.s3.amazonaws.com/images/pimod/sg-armv7-rpi-bullseye-testing-2023-341.zip)).
* **Raspberry Pi Imager** installed on your computer. Software is here: [https://www.raspberrypi.com/software/](https://www.raspberrypi.com/software/)
* A Raspberry Pi 2, 3, 4, or Zero 2 W.

## Flashing the software image to SD card

1. Insert the MicroSD card into the adapter and then in to the SD card reader.
   * If you’re using an external SD card reader, plug it in to your computer!
2. Open the Raspberry Pi Imager software and click on ‘Choose OS’. Scroll down to the bottom, click "Use custom", and navigate to the latest software that you just downloaded. You can select the .zip file even if you haven't yet unzipped it as the Imager will do that part for you.
3. After selecting the software, click on ‘Choose Storage’ and select the drive which corresponds to the SD card you plugged in.
4. Click ‘Write’. If the card is not empty, you will get a warning saying that all data will be erased. If you are okay with this, click ‘OK’. Once writing and verification is complete, you will be prompted to remove the card.

## Initial configuration

1. Ensure the Raspberry Pi is powered off and then insert the microSD card into the card slot and power it on.
2. When booted, you should see a Wi-Fi network appear that is named after the device serial number followed by "-init" (e.g. SG-1234RP56789-init). Connect to this network (no password is required) and then open a browser and navigate to: [https://192.168.7.2:88/](https://192.168.7.2:88/)
3. You will be prompted to enter a password which will apply to both the SensorGnome itself and the WiFi network. We recommend using the same password for the device and Wi-Fi for simplicity, but feel free to make them different.
4. Once you submit the form, you will be disconnected from the WiFi network and a new WiFi network will be seen, again comprised of the serial number, but lacking "-init" at the end. Connect to this new network, using the password you just assigned.
5. After connecting to the Wi-Fi again, navigate to [https://192.168.7.2:88/](https://192.168.7.2:88/) again to view the web interface.
6. When prompted, enter the password you previously assigned. The username is always `gnome` but should be pre-populated when you load the page.
7. Once configured, you can connect to the WiFi hotspot broadcast by the SG with a computer or smartphone to check status and modify any additional configuration.

## Basic management and configuration

1. After logging in you will be presented with dashboard with several ‘tabs’ at the top. These include:
   * **Overview:** selected by default
   * Radios: View and configure the radios attached other SG (e.g. FunCube dongles or CTT motus adapters)
   * **Files:** download data here
   * **Network:** Check or configure internet connection here
   * **Config:** Set the SensorGnome name and password here. Also enter your Motus credentials here if internet connected.
   * **Software:** check software version and update it. Also download logs here.

![](.gitbook/assets/0)

### Configure Wi-Fi

1. On the web interface, select the ‘Network’ tab.
2. Under the ‘Wi-Fi Client’ widget, click the pencil <img src=".gitbook/assets/1" alt="" data-size="line"> icon and edit the following inputs:
   1. **SSID**: the name of the Wi-Fi network (must match exactly)
   2. **Passphrase**: The Wi-Fi network password.
   3. **Country**: The 2-character ISO country code for your location. E.g.: Canada = CA; US = United States; for more codes see [https://en.m.wikipedia.org/wiki/ISO\_3166-1](https://en.m.wikipedia.org/wiki/ISO\_3166-1)
3. Click the green check mark <img src=".gitbook/assets/2" alt="" data-size="line"> once finished. You should see the status in the same widget change from ‘DISCONNECTED’ to ‘ASSOCIATING’ and then to ‘CONNECTED’. At the same time, the three widgets at the top left should read (from left to right) ‘OK’, ‘OK’, and ‘wifi’.

![](.gitbook/assets/3)

&#x20; 4\. Next, select the ‘Config’ tab.

&#x20; 5\. Under the “Sensorgnome Information” widget, click the pencil <img src=".gitbook/assets/4" alt="" data-size="line"> icon and edit the following inputs:

* **Upload username:** your Motus username.
* **Upload password:** your Motus password.

&#x20; 6\. Click the green check mark <img src=".gitbook/assets/5" alt="" data-size="line"> once finished. You should see the ‘Motus login’ status to the left read ‘OK’.

![](.gitbook/assets/6)

&#x20; 7\. If any data exist on the SensorGnome, you can upload it now by selecting the ‘Files’ tab and clicking the ‘Upload’ button.

![](.gitbook/assets/7)

:tada:  Congratulations, you have successfully connected your SensorGnome to the internet!
