# Transferring Detection Data

The raw radio data that the SensorGnome records consists of the individual radio pulses detected as well as some associated information, such as the precise time each pulse was detected, the USB port \(e.g. antenna\) it was detected on, and the strength of the signal. The data for each pulse is written on its own line in a text file, and then at the end of each hour the text file is compressed into a .gz file. All the detection files are then moved into a folder for each day that the SG was recording \(recall that the SG keeps time in UTC/GMT time\).

In order to identify the tags that may have been detected by the SG, the raw data must be copied from the SG and uploaded to the Motus server, where it is processed and cross-referenced against a database of known deployed tags.

_Note: we use the term “detection data” to refer to the raw radio data recorded by a SensorGnome. However it’s important to remember that in most cases, the vast majority of the “detection data” present will be product of background radio noise and not actual tag signals._

Transferring via an FTP connection is the recommended way of copying the raw detections. That allows you to check the live status of the SG on the Web Interface without turning the SensorGnome off.

1. Connect to your SensorGnome using the instructions above. Confirm you are connected by accessing the Web Interface. If you cannot access the Web Interface there is a very good chance you will not be able to establish an FTP connection either.
2. Open FileZilla and establish a connection following the instructions above.
3. Navigate to the SGdata folder where the detection data files are stored.
   1. **Raspberry Pi**
      * `/dev/sdcard/SGdata`
   2. **BeagleBone**
      * `/media/internal_SD_card/SGdata`
4. In the lower right panel, you should see a series of folders named for each date that the SG was recording data. Copy over all of the folders to a location on your computer so that it can be later uploaded to the Motus server to processing.
   * To quickly determining how much of the data you should copy from the SG to your computer, can you click on the station pin on the [Motus Receiver Map](https://motus.org/data/receiversMap?lang=en). The popup will tell you the last date for which there is data for this receiver. Copy over everything from today’s date back through to the “last data date”
   * The Motus server will ignore any duplicate data that gets uploaded, so if in doubt about how much of the data to transfer to your computer, err on the side of copying more than you think you actually need.
   * Typically you will not need to delete the data on the SG after copying over the files. And it can be helpful to leave a copy on the SG as a sort of backup in case the files on your computer are damaged or lost. But before leaving the data, refer to the available storage space on the card \(in the Web Interface\) to confirm there is still plenty of room. In normal circumstances, an SG will collect no more than a few gigabytes of data per year.

