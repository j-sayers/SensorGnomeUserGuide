# Downloading detection data

The raw radio data that the SensorGnome records consists of the individual radio pulses detected, as well as some associated information, such as the precise time each pulse was detected, the USB port \(e.g. antenna\) it was detected on, and the strength of the signal. The data for each pulse is written on its own line in a text file, and then at the end of each hour the text file is compressed into a _.gz_ file. All the detection files are then moved into a folder for each day that the SG was recording \(recall that the SG keeps time in UTC/GMT time\).

In order to identify the tags that have been detected by the SG, the raw data must be copied from the SG and uploaded to the Motus server, where it is processed and cross-referenced against a database of known deployed tags. Many newer stations, and in particular Motus stations powered by CTT SensorStations, are connected to the internet and sync their data to the Motus server on an automated schedule. However the majority of Motus stations still require a physical visit in order to download data from the receiver. 

{% hint style="info" %}
We use the term “detection data” to refer to the raw radio data recorded by a SensorGnome. However it’s important to remember that in most cases, the vast majority of the “detection data” present will be product of background radio noise and not actual tag signals.
{% endhint %}

### Where does a SensorGnome save detection data?

Raspberry Pi and BeagleBone based SensorGnomes save their detection data in slightly different places. Usually, this is on the MicroSD card, but there are some subtle differences between the two that can be quite important.

{% tabs %}
{% tab title="Raspberry Pi" %}
RPi SensorGnomes save detection data on the MicroSD card. This is the _only_ place where detection data can be found as the RPi has no internal storage of its own. The software which runs the SG is also stored on the MicroSD card.

#### Detection data \(SGdata\) folder

* FTP connection \(e.g. in FileZilla\)
  * `/dev/sdcard/SGdata`
* Directly on MicroSD card when removed from powered-down RPi
  * `/SGdata`
{% endtab %}

{% tab title="BeagleBone" %}
A BeagleBone has its own internal storage; this is what the SG software is installed on. However it is a limited amount of storage \(only 2GB or 4GB, depending on the BB, and much of that is used up by the software\), so detection data is usually stored on the MicroSD card. 

#### Detection data \(SGdata\) folder on the MicroSD card

* FTP connection \(e.g. in FileZilla\)
  * `/media/internal_SD_card/SGdata`
* Shared network drive \(e.g. in Windows Explorer\)
  * `\\192.168.7.2\data\internal_SD_card\SGdata`
* Directly on the MicroSD card
  * `/SGdata`

Sometimes a BeagleBone is unable to recognize or write to a MicroSD card. In this case the BeagleBone will write to a different folder on the internal storage. When you copy data from this folder, be sure to delete it when finished since the BB can fail to record if its internal storage is completely full.

#### Internal detection data folder \(when MicroSD card is absent or can't be read\)

* FTP connection \(e.g. in FileZilla\)
  * `/media/internal_system_memory/SGdata`
* Shared network drive \(e.g. in Windows Explorer\)
  * **`\\192.168.7.2\data\internal_system_memory\SGdata`**
{% endtab %}
{% endtabs %}

{% hint style="info" %}
When you copy the detection data onto your computer, put it in a folder with a meaningful name that contains both the name of the station/site and the date the station was visited. The ensures that you can easily recognize the data on your computer and find notification emails \(and the handy links they contain\) in your email.
{% endhint %}

## Option 1: Transferring over FTP Connection

Transferring via an FTP connection is the recommended way of copying the data files. That allows you to check the live status of the SG on the Web Interface without turning the SensorGnome off, and gives you a better sense of the state you are leaving the station in. If you cannot establish an FTP connection, there are a couple other options to copy the data; these are described later in this chapter.

**1\)** Connect to your SensorGnome using the instructions above. Confirm you are connected by accessing the Web Interface. If you cannot access the Web Interface there is a very good chance you will not be able to establish an FTP connection either.

**2\)** Open FileZilla and establish a connection following the instructions above. In FileZilla, navigate to the SGdata folder where the detection data files are stored. 

{% tabs %}
{% tab title="Raspberry Pi" %}
`/dev/sdcard/SGdata`
{% endtab %}

{% tab title="BeagleBone" %}
`/media/internal_SD_card/SGdata`
{% endtab %}
{% endtabs %}

**3\)** In the lower right panel, you should see a series of folders named for each date that the SG was recording data. Copy over all of the folders to a location on your computer so that it can be later uploaded to the Motus server to processing. Give the folder on your computer a meaningful name, such as "Site Name 2021-02-03", including the site name and the date you downloaded the data.

![SGdata folder on a RPi SG](.gitbook/assets/sgdata.png)

* To quickly determining how much of the data you should copy from the SG to your computer, can you click on the station pin on the [Motus Receiver Map](https://motus.org/data/receiversMap?lang=en). The popup will tell you the last date for which there is data for this receiver. Copy over everything from today’s date back through to the “last data date”
* The Motus server will ignore any duplicate data that gets uploaded, so if in doubt about how much of the data to transfer to your computer, err on the side of copying more than you think you actually need.
* Typically you will not need to delete the data on the SG after copying over the files. And it can be helpful to leave a copy on the SG as a sort of backup in case the files on your computer are damaged or lost. But before leaving the data, refer to the available storage space on the card \(in the Web Interface\) to confirm there is still plenty of room. In normal circumstances, an SG will collect no more than a few gigabytes of data per year.

## Option 2: Copying directly from the MicroSD card

With both Raspberry Pi and BeagleBone SensorGnomes it's possible to copy detection data files directly from the MicroSD card. Usually this isn't the preferred method since it introduces more potential for problems, but it works just fine as long as you pay attention to a few of the details.

**1\)** Completely power down the SG by disconnecting the power source\(s\) from the RPi or BB. A RPi has just one power source, supplied through the micro USB; a BB can be powered by either the "barrel jack" or the mini USB so make sure both are disconnected if applicable.

{% hint style="warning" %}
Ensure that the RPi or BB is fully powered down prior to removing or inserting the MicroSD card. Failure to do so may result in loss of data.
{% endhint %}

**2\)** Remove the MicroSD card from the SG. For some RPi the MicroSD is deeply recessed in the case and difficult to remove without tweezers. You may also see a sticker saying something like "Do not remove this card".

**3\)** Insert the MicroSD card into your computer. Most computers do not have a designated slot for reading this side card so an adapter is likely needed.

**4\)** Navigate to the appropriate folder and copy the data files. There is generally no need to delete the files on the card unless it is running low on storage space. 

**5\)** Replace the MicroSD card 

{% hint style="danger" %}
For Raspberry Pi SGs, make sure that the card you are replacing has the SG software on it. Without the proper software on the card, the SG will not work properly even though you may see lights on. Do not put a blank MicroSD card into a RPi.
{% endhint %}

**6\)** Power on the SG. Check the Web Interface after you are done to confirm everything is working properly.

## Option 3: Copying detection data stored internally \(BeagleBone only\)

In normal operating conditions a BeagleBone SG saves detection data on a MicroSD card. However there are occasions where the card cannot be read by the BB, or the card is absent altogether. In these cases, the BeagleBone SG will revert to storing detection data on its internal storage. This works in the short term, but the internal storage space on a BB is limited, and when the storage is full the BB may cease functioning altogether. For this reason, always delete the data stored internally after you have copied it. 

There are two methods of accessing the internal storage of a BB:

**1\)** Accessing the BeagleBone as a **shared network drive** in Windows Explorer or the Mac equivalent. Here you can view and manipulate files just as you would on your computer.

* Internal storage folder path
  * **`\\192.168.7.2\data\internal_system_memory\SGdata`**

**2\)** Running the BB SG with a "**Rescue Image**", which is a bootable software card. Once the BB is running, you can connect to it with an FTP connection and view the Web Interface as you normally would.

* Internal storage folder path
  * `/media/internal_system_memory/SGdata`

