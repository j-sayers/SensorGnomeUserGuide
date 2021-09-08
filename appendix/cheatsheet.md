# Connection and folder path cheatsheet

This is a complete reference of the network addresses and folder paths, organized by receiver type \(RPi vs BB\) and method of connection.

{% tabs %}
{% tab title="Raspberry Pi " %}
## Raspberry Pi SensorGnome

### Web Interface \(Firefox or Chrome browser\)

* Wi-Fi Hotspot
  * `http://192.168.7.2`
* Ethernet cable
  * `http://sgpi.local`

### Establishing FTP connection \(e.g. with FileZilla\)

* Wi-Fi hotspot
  * host: `sftp://192.168.7.2`
  * username: `root`
  * password: `root`
* Ethernet cable
  * host: `sftp://sgpi.local`
  * username: `root`
  * password: `root`

### Detection data \(SGdata\) folder

* FTP connection \(e.g. in FileZilla\)
  * `/dev/sdcard/SGdata`
* Directly on MicroSD card when removed from powered-down RPi
  * `/SGdata`

### _uboot_ folder \(configuration files\)

* FTP connection \(e.g. in FileZilla\)
  * `/dev/sdcard/uboot`
* Directly on MicroSD card when removed from powered-down RPi
  * `/uboot`
{% endtab %}

{% tab title="BeagleBone" %}
## BeagleBone SensorGnome

### Web Interface \(Firefox or Chrome browser\)

* USB \(mini USB to standard USB\)
  * `http://192.168.7.2`
* Ethernet cable 
  * `http://192.168.9.2`

### Establishing FTP connection \(e.g. with FileZilla\)

* USB \(mini USB to standard USB\)
  * host: `sftp://192.168.7.2`
  * username: `root`
  * password: `root`
* Ethernet Cable \(network must first be configured\)
  * host: `sftp://192.168.9.2`
  * username: `root`
  * password: `root`

### Detection data \(SGdata\) folder on the MicroSD card

* FTP connection \(e.g. in FileZilla\)
  * `/media/internal_SD_card/SGdata`
* Shared network drive \(e.g. in Windows Explorer\)
  * `\\192.168.7.2\root\media\internal_SD_card\SGdata`

### Internal detection data folder \(when MicroSD card is absent or can't be read\)

* FTP connection \(e.g. in FileZilla\)
  * `/media/internal_system_memory/SGdata`
* Shared network drive \(e.g. in Windows Explorer\)
  * `\\192.168.7.2\root\media\internal_system_memory\SGdata`

### _uboot_ folder \(configuration files\)

* FTP connection \(e.g. in FileZilla\)
  * `/boot/uboot`
* Shared network drive \(e.g. in Windows Explorer\)
  * `\\192.168.7.2\root\boot\uboot\`
{% endtab %}
{% endtabs %}

