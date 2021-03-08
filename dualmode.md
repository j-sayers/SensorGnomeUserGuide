# CTT LifeTag compatibility \(dual-mode\)

By default a SensorGnome is capable of detecting only Lotek Nanotags. However by applying a software patch a SensorGnome can also detect CTT LifeTags/ PowerTags. We refer to SGs that are listening for both tag types as “dual-mode” SensorGnomes. CTT compatibility is most reliably accomplished with a RPi SG. 

_Note: you will not be able to use the same dongles for CTT tags as you use for Lotek tags. For CTT-compatible dongles, contact CTT or Birds Canada._

**Raspberry Pi SensorGnome**

1. Download the CTT compatibility patch
   * Direct download link: [2019-11-12-rpi\_ctt\_dongle.tar.bz2](https://s3.amazonaws.com/media.celltracktech.com/sensorgnome/raspberry/2019-11-12-rpi_ctt_dongle.tar.bz2)
2. Rename the file to “sensorgnome\_update.tar.bz2”
3. Connect to the RPi SG using the WiFi Hotpot or Ethernet
4. Open FileZilla and establish an FTP connection with the SG
5. On the top right panel navigate to the uboot folder

   uboot Folder for a BeagleBone SG

6. In the lower right hand pane in FileZilla, copy the “sensorgnome\_update.tar.bz2” file into this folder
7. Power down the SG and reboot the SG
8. Connect to the SG and open the Web Interface. If you have a CTT compatibility dongle plugged in you should see it in the Web Interface

If successful you should see the CTT dongle attached in the “Devices” section. You will **not** see it in the “What I’m doing now” section. You may see CTT tag ID’s \(real tags, or even false positives due to noise\) in the “Live Known Tags” section. However this section, along with the “What I’m doing now” section, are only displayed if a FunCUBE dongle is attached.

_Note: it often requires two complete boot cycles of the SG for this process to succeed._

