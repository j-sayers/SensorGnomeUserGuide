# Appendix: Connection and folder path reference

This is a quick reference of the methods used to connect to an SG and to navigate to the various folders

* **Raspberry Pi SensorGnome**
  * Connecting to your computer \(Firefox or Chrome browser\)
    * Wi-Fi Hotspot
      * `http://192.168.7.2`
    * Ethernet cable
      * `http://sgpi.local`
  * Establishing FTP connection
    * Using Wi-Fi hotspot
      * host: `sftp://192.168.7.2`
      * username: `root`
      * password: `root`
    * Using Ethernet cable
      * host: `sftp://sgpi.local`
      * username: `root`
      * username: `root`
  * Detection Data folder
    * FTP connection
      * `/dev/sdcard/SGdata`
    * Directly on MicroSD card
      * `/SGdata`
  * uboot folder
    * FTP connection
      * `/dev/sdcard/uboot`
    * Directly on MicroSD card
      * `/uboot`
* **BeagleBone SensorGnome**
  * Connecting to your computer
    * USB
      * `http://192.168.7.2`
    * Shared network drive
      * NA?
  * Establishing FTP connection
    * USB
      * host: `sftp://192.168.7.2`
    * Shared network drive
      * NA?
  * Detection Data folder
    * FTP Connection
      * `/media/internal_SD_card/SGdata`
    * Shared network drive
      * `\\192.168.7.2\data\internal_SD_card\SGdata`
  * uboot folder
    * FTP Connection
      * `/boot/uboot`
    * Shared network drive
      * `\\192.168.7.2\root\boot\uboot\`

