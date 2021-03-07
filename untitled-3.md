# Transferring Detection Data

The raw radio data that the SensorGnome records consists of the individual radio pulses detected, as well as some associated information, such as the precise time each pulse was detected, the USB port \(e.g. antenna\) it was detected on, and the strength of the signal. The data for each pulse is written on its own line in a text file, and then at the end of each hour the text file is compressed into a _.gz_ file. All the detection files are then moved into a folder for each day that the SG was recording \(recall that the SG keeps time in UTC/GMT time\).

In order to identify the tags that have been detected by the SG, the raw data must be copied from the SG and uploaded to the Motus server, where it is processed and cross-referenced against a database of known deployed tags. Many newer stations, and in particular CTT SensorStations, are connected to the internet and sync their data to the Motus server on an automated schedule. However the majority of Motus stations still require a physical visit in order to download data from the receiver. 

{% hint style="info" %}
_We use the term “detection data” to refer to the raw radio data recorded by a SensorGnome. However it’s important to remember that in most cases, the vast majority of the “detection data” present will be product of background radio noise and not actual tag signals._
{% endhint %}

### Where does a SensorGnome save detection data?

Raspberry Pi and BeagleBone based SensorGnomes save their detection data in slightly different places. Usually, this is on the MicroSD card, but there are some subtle differences between the two that can be quite important.

{% tabs %}
{% tab title="Raspberry Pi" %}
RPi SensorGnomes save detection data on the MicroSD card. This is the _only_ place where detection data can be found as the RPi has no internal storage of its own.

#### Folder path:

* via FTP \(e.g. with FileZilla\)
  * `/dev/sdcard/SGdata`
* directly on the SD card when inserted into a computer
  * 
{% endtab %}

{% tab title="BeagleBone" %}

{% endtab %}
{% endtabs %}



Transferring via an FTP connection is the recommended way of copying the data files. That allows you to check the live status of the SG on the Web Interface without turning the SensorGnome off, and gives you a better sense of the state you are leaving the station in. If you cannot establish an FTP connection, there are a couple other options to copy the data; these are described later in this chapter.

## Option 1: Transferring over FTP Connection

**1\)** Connect to your SensorGnome using the instructions above. Confirm you are connected by accessing the Web Interface. If you cannot access the Web Interface there is a very good chance you will not be able to establish an FTP connection either.

**2\)** Open FileZilla and establish a connection following the instructions above. In FileZilla, navigate to the SGdata folder where the detection data files are stored. 

* **Raspberry Pi**
  * `/dev/sdcard/SGdata`
* **BeagleBone**
  * `/media/internal_SD_card/SGdata`

**3\)** In the lower right panel, you should see a series of folders named for each date that the SG was recording data. Copy over all of the folders to a location on your computer so that it can be later uploaded to the Motus server to processing. Give the folder on your computer a meaningful name, such as "Site Name 2021-02-03", including the site name and the date you downloaded the data.

* To quickly determining how much of the data you should copy from the SG to your computer, can you click on the station pin on the [Motus Receiver Map](https://motus.org/data/receiversMap?lang=en). The popup will tell you the last date for which there is data for this receiver. Copy over everything from today’s date back through to the “last data date”
* The Motus server will ignore any duplicate data that gets uploaded, so if in doubt about how much of the data to transfer to your computer, err on the side of copying more than you think you actually need.
* Typically you will not need to delete the data on the SG after copying over the files. And it can be helpful to leave a copy on the SG as a sort of backup in case the files on your computer are damaged or lost. But before leaving the data, refer to the available storage space on the card \(in the Web Interface\) to confirm there is still plenty of room. In normal circumstances, an SG will collect no more than a few gigabytes of data per year.

## Option 2: Copying directly from the MicroSD card

With both Raspberry Pi and BeagleBone SensorGnomes it's possible to copy detection data files directly from the MicroSD card. Usually this isn't the ideal method since it introduces more potential for problems. But 

{% hint style="danger" %}
Ensure that the RPi or BB is fully powered down prior to removing or inserting the MicroSD card. Failure to do so may result in loss of data.
{% endhint %}

## Option 3: Accessing the SG as a shared network drive \(BeagleBone only\)



