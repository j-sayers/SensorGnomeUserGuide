# Updating Software

One of the first steps in troubleshooting is to ensure that you have the most up-to-date software installed on your SensorGnome. Aside from ensuring your SG is up-to-date – this entire guide as based on the premise that you are using the most recent software – reinstalling the most recent software can resolve many issues.

## Raspberry Pi SensorGnome

For Raspberry Pi SensorGnomes, the software runs entirely off the MicroSD card; if the proper software isn’t present on the MicroSD card, the RPi SG won’t function properly. This can cause issues for teams who are unaware of this – and who expect to be able to simply swap out one card without ensuring that the new card has the proper software on it. But it also makes updating the software with a clean installation very simple; all you need to do is copy the software files onto a blank SD card.

{% hint style="warning" %}
Always ensure that the MicroSD card you use with an RPi SG has the software copied onto it. The RPi SG runs _exclusively_ from the software SD card, so if a blank SD card is used, the SG won't record any data \(though you may still still lights flashing on the RPi\).
{% endhint %}

1. Download the most recent Raspberry Pi SG software. Currently this is the 2018-10-12 version.
   * Direct download link: [SGPI-2018-10-12\_LIWIXI.ZIP](https://public.sensorgnome.org/Raspberry_Pi_Sensorgnome/SGPI-2018-10-12_LIWIXI.ZIP)
   * This is a compressed .zip file which will need to be “unzipped” prior to use. Most modern computers come equipped with the ability to handle .zip files.
2. Insert a blank or recently formatted MicroSD into your computer.
3. Copy the _entire_ contents of the .zip over to the _root level_ of MicroSD card. After copying over, the contents of the MicroSD card should look like the image below

   Copy the contents of the .zip file to the root level of the MicroSD card

4. You can now insert the MicroSD card into the slot in the RPi. Once the MicroSD card is in place, power up the RPi and proceed to connect to it and check the Web Interface.

![The MicroSD card \(highlighted in red\) is inserted with the contacts facing up](.gitbook/assets/rpisdslot.jpg)

## BeagleBone SensorGnome

The software that runs the BeagleBone SG is installed onto the internal memory of the BeagleBone. In order to upgrade or re-install the software you need to make a designated installation disk which contains the software image on a MicroSD card. Upgrading the BB in this way is referred to as _re-imaging_ the BeagleBone. Reimaging a BB will overwrite whatever existing software is already installed on the BB. However it will not overwrite any detection data present on the BB SG, so it can be a helpful first step in “refreshing” a BB SG that you are having trouble connecting to.

###  **Creating an image disk**

1. Download the latest software version for the BB SG. Currently this is the 2017-03-16 version.
   * Direct download link: [sensorgnome\_image\_2017-03-06\_15-33-00.img.7z](https://public.sensorgnome.org/Beaglebone_Sensorgnome_Images/sensorgnome_image_2017-03-06_15-33-00.img.7z)
2. This file is a compressed .7z file. In order to uncompress it you will need 7zip installed. Your computer may already have this installed, but if not, [you can find it at this link](https://www.7-zip.org/). The uncompressed file will have an .img extension.
3. Download [balenaEtcher](https://www.balena.io/etcher/?), and click “Select Image,” where you can select the the .img file
4. Select the MicroSD card in the next step, and then click “Flash!” This will overwrite any data that happens to be on the target MicroSD card so make sure you have everything copied over that you need.
5. Once the process is complete, you may get a computer popup warning that the MicroSD card is corrupted and needs to be formatted. This is expected as the file format is no longer compatible with a Windows or Mac computer

###  Updating / r**eimaging the BeagleBone**

1. Ensure that the BeagleBone is completely powered down \(both the Mini USB and “barrel jack” are capable of powering the BeagleBone\).
2. Insert the image card into the BeagleBone and power on.
3. The 4 blue LED lights above the mini USB connection on the BeagleBone will begin flashing in a sporadic pattern. After a few seconds, all 4 LED’s will flash on/off in unison several times. This indicates that the process of writing the software to the BB is beginning.
4. The LEDs will begin flashing in a “crawling” or “wave” light pattern from one end to the other. This should continue for several minutes.
5. When the process is complete, all 4 LED lights will remain on. You can now power down the BB and remove the installation card.
6. Power up the BB again \(without the image card\) and visit the Web Interface to confirm everything worked.

