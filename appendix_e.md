# Appendix E: Using the Rescue Image on a BeagleBone SG

## Why a rescue image?

If you have a BeagleBone which no longer boots or to which you can no longer connect, you can use one of the "rescue" images to burn a micro SD card, and boot from that. The SG will then operate as normal, but will not re-image the internal flash memory.

Normally, BeagleBone computers store their software on an internal flash storage device, but sometimes the internal storage is corrupted and does not allow new software to be written to it. In this case, you will not be able to use your SensorGnome unless you use a **rescue image**. This is a software image which remains on the SD card rather than being installed in the internal storage. This functions in much the same way as would a Raspberry Pi which also stores its software on the SD card. The important part here is that the SD card with the rescue image must remain in the device at all times.

## Making a rescue image

This is done in much the same way as a regular software image for the BeagleBone, it's just a different file. 

1. Download and unzip the rescue image here: [sensorgnome\_rescue\_image\_2017-03-06\_15-33-00.img.7z](https://public.sensorgnome.org/Beaglebone_Sensorgnome_Images/sensorgnome_rescue_image_2017-03-06_15-33-00.img.7z)
   * If you don't have 7Zip, you can download it here: [https://www.7-zip.org/](https://www.7-zip.org/)
2. Download [balenaEtcher](https://www.balena.io/etcher/?), a free and open-sourced program for creating disk images, and click “Select Image,” where you can select the the _.img_ file
3. Select the MicroSD card in the next step, and then click “Flash!”.
4. Once flashing has completed, safely remove the card from your computer.
5. Make sure the BeagleBone is powered off and then insert the SD card.
6. Power on the BeagleBone and give it a minute or two to boot.
7. Once booting is complete, you're good to go!

