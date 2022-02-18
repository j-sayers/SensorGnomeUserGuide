# Installing and updating SensorGnome software

One of the first steps in troubleshooting is to ensure that you have the most up-to-date software installed on your SensorGnome. Aside from ensuring your SG is up-to-date – this entire guide as based on the premise that you are using the most recent software – reinstalling the most recent software can resolve many issues.

{% tabs %}
{% tab title="Raspberry Pi" %}
## Raspberry Pi SensorGnome

For Raspberry Pi SensorGnomes, the software runs entirely off the MicroSD card; if the proper software isn’t present on the MicroSD card, the RPi SG won’t function properly. This can cause issues for teams who are unaware of this – and who expect to be able to simply swap out one card without ensuring that the new card has the proper software on it. But it also makes updating the software with a clean installation very simple; all you need to do is copy the software files onto a blank SD card.

{% hint style="warning" %}
Certain SD cards models have failed when running on Rasperry Pis. To reduce the likelihood of an SD card failure, try to use [an SD card from this list of known models](https://elinux.org/RPi\_SD\_cards#Working\_.2F\_Non-working\_SD\_cards).
{% endhint %}

{% hint style="danger" %}
Always ensure that the MicroSD card you use with an RPi SG has the software copied onto it. The RPi SG runs _exclusively_ from the software SD card, so if a blank SD card is used, the SG won't record any data (though you may still still lights flashing on the RPi).
{% endhint %}

**1)** Download the most recent Raspberry Pi SG software. Currently this is the October 12, 2018 version.

* Direct download link: [SGPI-2018-10-12\_LIWIXI.ZIP](https://public.sensorgnome.org/Raspberry\_Pi\_Sensorgnome/SGPI-2018-10-12\_LIWIXI.ZIP)
* This is a compressed .zip file which will need to be “unzipped” prior to use. Most modern computers come equipped with the ability to handle .zip files.

**2)** Insert a blank or recently formatted MicroSD into your computer.

**3)** Copy the _entire_ contents of the .zip over to the _root level_ of MicroSD card. After copying over, the contents of the MicroSD card should look like the image below

![Copy the contents of the .zip file onto the MicroSD card](.gitbook/assets/rpifolder.png)

**4)** Copy the contents of the .zip file to the root level of the MicroSD card

**5)** You can now insert the MicroSD card into the slot in the RPi. Once the MicroSD card is in place, power up the RPi and proceed to connect to it and check the Web Interface.

![The MicroSD card (highlighted in red) is inserted with the contacts facing up](.gitbook/assets/rpisdslot.jpg)
{% endtab %}

{% tab title="BeagleBone" %}
## BeagleBone SensorGnome

The software that runs the BeagleBone SG is installed onto the internal storage of the BeagleBone. In order to upgrade or re-install the software you need to use a designated installation disk which contains the software image on a MicroSD card. This process is often referred to as _re-imaging_ the BeagleBone. Re-imaging a BB SG will overwrite whatever existing software is already installed on the BB. However it will not overwrite any detection data present on the BB SG, so it can be a helpful first step in restoring a BB SG that you are having trouble connecting to.

### **Creating an image disk**

**1)** Download the latest software version for the BB SG. Currently this is the 2017-03-16 version. Direct download link: [sensorgnome\_image\_2017-03-06\_15-33-00.img.7z](https://public.sensorgnome.org/Beaglebone\_Sensorgnome\_Images/sensorgnome\_image\_2017-03-06\_15-33-00.img.7z)

This file is a compressed _.7z_ file. In order to uncompress it you will need 7zip installed. Your computer may already have this installed, but if not, [you can find it at this link](https://www.7-zip.org). The uncompressed file will have an _.img_ extension.

**2)** Download [balenaEtcher](https://www.balena.io/etcher/?), a free and open-sourced program for creating disk images, and click “Select Image,” where you can select the the _.img_ file.&#x20;

**3)** Select the MicroSD card in the next step, and then click “Flash!”.

{% hint style="warning" %}
This will overwrite any data that happens to be on the target MicroSD card so make sure you have everything copied over that you need.
{% endhint %}

![The BB SG img file and the MicroSD card are both selected and ready to be flashed](<.gitbook/assets/betcher (1) (2) (2) (2) (2) (2) (2) (2) (2) (2) (2) (1).png>)

**4)** Once the process is complete, you may get a computer popup warning that the MicroSD card is corrupted and needs to be formatted. This is expected as the file format is no longer compatible with a Windows or Mac computer.

### Re-imaging **the BeagleBone**

Once you have your image card, you can use it to update or re-image the BeagleBone SG.

**1)** Ensure that the BeagleBone is completely powered down. A BeagleBone has two possible power sources (mini USB and “barrel jack”); ensure that both are disconnected from power.

1.  Ensure that the BeagleBone is completely powered down. A BeagleBone has two possible power sources (mini USB and “barrel jack”); ensure that both are disconnected from power.

    ![](<.gitbook/assets/bbpower (1) (2).jpg>)
2. Insert the imaged microSD card in to the slot of the BeagleBone.
3. **If this is the first time you are installing software** (or if you want to do a "clean" install) you must hold down the boot button for several seconds while powering on the SensorGnome. Otherwise, just plug in the BeagleBone and wait for it to boot up.![](.gitbook/assets/=beaglebone\_black\_image\_showing\_boot\_button.jpg)
4.  Once powered on, the 4 blue LED lights above the mini USB connection will begin flashing in a sporadic/sporadic pattern. After a few seconds, all 4 LED’s will flash on/off in unison several times. This indicates that the process of writing the software to the BB is beginning.

    ![](.gitbook/assets/leds\_flash.gif)

    &#x20;All 4 LED lights flash in unison when re-imaging begins
5.  Then, the LEDs will begin flashing in a “crawling” or “wave” light pattern from one end to the other. This should continue for several minutes.&#x20;

    ![](.gitbook/assets/leds\_crawl.gif)
6. When the process is complete, all 4 LEDs will light up and remain on. You can now power down the BB and remove the installation card.
7. Power up the BB again (without the image card) and visit the Web Interface to confirm everything is working

{% hint style="warning" %}
If the "crawling" pattern only lasts for a few seconds it is quite likely that the re-imaging process failed. [Refer here](appendix/rescue.md) for tips on how to recover a BB in this state.
{% endhint %}
{% endtab %}
{% endtabs %}
