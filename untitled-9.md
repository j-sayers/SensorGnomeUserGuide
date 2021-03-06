# Appendix: Connection and folder path Cheetsheat

This is a quick reference of the network addresses and folder paths, organized by receiver type \(RPi vs BB\) and method of connection.

{% tabs %}
{% tab title="Raspberry Pi SensorGnome" %}
### Raspberry Pi SensorGnome

#### Web Interface \(Firefox or Chrome browser\)

* Wi-Fi Hotspot
  * `http://192.168.7.2`
* Ethernet cable
  * `http://sgpi.local`

#### Establishing FTP connection \(e.g. with FileZilla\)

* Wi-Fi hotspot
  * host: `sftp://192.168.7.2`
  * username: `root`
  * password: `root`
* Ethernet cable
  * host: `sftp://sgpi.local`
  * username: `root`
  * password: `root`

#### Detection data \(SGdata\) folder

* via FTP connection \(e.g. in FileZilla\)
  * `/dev/sdcard/SGdata`
* Directly on MicroSD card when removed from powered-down RPi
  * `/SGdata`

#### uboot folder \(configuration files\)

* via FTP connection \(e.g. in FileZilla\)
  * `/dev/sdcard/uboot`
* Directly on MicroSD card when removed from powered-down RPi
  * `/uboot`
{% endtab %}

{% tab title="BeagleBone SensorGnome" %}
### BeagleBone SensorGnome

#### Web Interface \(Firefox or Chrome browser\)

* USB \(mini USB to standard USB\)
  * `http://192.168.7.2`
* Ethernet cable \(network must first be configured\)
  * `http://192.168.9.2`
* Shared network drive \(e.g. in Windows Explorer\)
  * NA?

#### Establishing FTP connection \(e.g. with FileZilla\)

* USB \(mini USB to standard USB\)
  * host: `sftp://192.168.7.2`
  * username: `root`
  * password: `root`
* Ethernet Cable \(network must first be configured\)
  * host: `sftp://notsure!!!`
  * username: `root`
  * password: `root`

#### Detection data \(SGdata\) folder

* via FTP connection \(e.g. in FileZilla\)
  * `/media/internal_SD_card/SGdata`
* Shared network drive \(e.g. in Windows Explorer\)
  * `\\192.168.7.2\data\internal_SD_card\SGdata`

#### Internal detection data folder \(when MicroSD card is absent or can't be read\)

* via FTP connection \(e.g. in FileZilla\)
  * **`/media/internal_system_memory/SGdata`**
* Shared network drive \(e.g. in Windows Explorer\)
  * **`\\192.168.7.2\data\internal_system_memory\SGdata`**

#### uboot folder \(configuration files\)

* via FTP connection \(e.g. in FileZilla\)
  * `/boot/uboot`
* Shared network drive \(e.g. in Windows Explorer\)
  * `\\192.168.7.2\root\boot\uboot\`
{% endtab %}
{% endtabs %}

