---
description: >-
  How to change the frequency setting for FunCubes to configure a SensorGnome or
  SensorStation to detect Lotek tags outside the Western Hemisphere
---

# Configuring the SensorGnome frequency

{% hint style="danger" %}
This is a critical step for any SensorGnome (or SensorStation) listening for Lotek tags outside the Western Hemisphere. This only affects Lotek compatible radios (e.g. FunCube, RTL-SDR, etc) and tags.&#x20;
{% endhint %}

There are three frequencies worldwide that Motus-compatible Lotek tags broadcast on. The default configuration is set to the Western Hemisphere frequency so any SG or SensorStation deployed elsewhere needs to be configured to listen to the appropriate frequency for that region if listening for Lotek tags.

However, the frequency saved in the SG is not actually the true frequency of the tag, but rather that value minus 4 kHz. This is because the FunCubes actually resolve the tag signals better if tuned slightly below the actual frequency. For example, you'll notice that if the frequency is set for 166.380, the value here will be 166.374 and if the frequency set in the UI is 150.1, the value here will be 150.096.&#x20;

{% hint style="warning" %}
The FunCube frequency needs to be set 4 kHz **below** the actual frequency
{% endhint %}

| Region             | Actual frequency | FunCube setting |
| ------------------ | ---------------- | --------------- |
| Western Hemisphere | 166.380          | 166.376         |
| Europe and UK      | 150.1            | 150.096         |
| Australia          | 155.5            | 155.496         |

## How to set the frequency

### On a SensorGnome

The current frequency setting is displayed in the web interface. However the interactive control to change this here does not always work.&#x20;

Instead, the frequency setting usually has to be modified directly in the configuration file stored on the SG called `deployment.txt`.&#x20;

{% hint style="info" %}
On a RPi SG the deployment.txt file can be modified directly on the MicroSD card either before or after first use by navigating to `uboot` folder. This is generally easier than connecting to the SG if it's an option.&#x20;
{% endhint %}

**1)** [Connect to the SG using your preferred method](../connecting.md)

**2)** [Establish an FTP connection ](../ftp.md)

**3)** Navigate to the configuration folder (`/dev/sdcard/uboot` on Raspberry Pi or `/boot/uboot` on BeagleBone

4\) Download the `deployment.txt` file to your computer and modify the frequency setting. There are four places where this is set. Three settings for the various dongles (FunCube Pro, FunCube Pro Plus, and RTL-SDR). These are set to the actual frequency minus 4 kHz, as described above. The fourth setting is at the very bottom of the file and is set to the actual frequency. These settings should be found on or around lines 52, 218, 314, and 364 of the `deployment.txt` file.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>The frequency setting for the FunCube Pro Plus dongle on line 218</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>The frequency setting at the bottom of the file. Note this is the <em>actual</em> frequency.</p></figcaption></figure>

5\) Save the file and re-upload the file back to the `uboot` folder, overwriting the existing file.

6\) Power down the SG and reboot, then connect it to your computer and open the `deployment.txt` file on the SG to ensure that the changes were persistent. You should also see the change reflected in the web interface.

### On a SensorStation

On a SensorStation, this can be modified via the web interface. Generally that is accessed at `http://sensorstation.local` while connected to the SensorStation with an Ethernet cable. At the bottom of the main page is a window containing the contents of the `deployment.txt` file. Changes can be made directly in the window. After saving, it's best to reboot your SS and reconnect to confirm the persistence of the setting change. Full instructions for accessing and understanding the SensorStation's web interface can be found on the [official guide.](https://cellular-tracking-technologies.github.io/ctt\_documentation/SensorStation-User-Guide.html#the-sensorstation-interface-explained)

