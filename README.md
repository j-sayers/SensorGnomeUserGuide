---
description: >-
  This document explains how to connect to your SensorGnome, check its status
  via the Web Interface, download detection data, update the software, and
  modify configuration files.
---

# Introduction and Overview

## What is a SensorGnome?

A SensorGnome is an automated radio receiver, designed to detect and record radio signals transmitted by wildlife tracking tags, without the need for any person to be present. 

## How to use this guide

Generally each time you work with a SensorGnome – either deployed in the field or as a test on your desktop – you will perform the same basic steps below. 

**1\)** Connect the SensorGnome to your computer

**2\)** Open the Web Interface in a browser to check the SG's initial status

**3\)** Establish an FTP connection to download detection data or modify configuration files. 

**4\)** Confirm status once again on the Web Interface \(and take a photo or screenshot\)

**5\)** Disconnect from the SensorGnome

There are many similarities between Raspberry Pi and BeagleBone based SensorGnomes – in terms of the hardware, the software that powers them, and the process of using them typically follows the same outline. But there are also some key differences, particularly as it relates to the method of connecting to them and transferring data. 

The steps above are described in detail in this guide, with an effort to presenting the commonalities between the two receiver types. Where differences are found between RPi and BB SensorGnomes, they will be broken down into sub-sections. Additional tasks, which aren't necessarily performed on a regular basis, are provided in various appendices. 

![Toggle between RPi and BB instructions using the tabs](.gitbook/assets/tabs.jpg)

## What kind of SensorGnome do I have?

The BeagleBone and Raspberry Pi computers may be housed in a variety of cases that may have different colours and labels on them. However they are easily differentiated by the ports that they have, as shown in the images below. 

A **Raspberry Pi** \(below\) has one Ethernet port on the left, with **4 standard USB ports** to the right of the Ethernet port.

![Raspberry Pi](.gitbook/assets/rpi.jpg)

A **BeagleBone** \(below\) has one Ethernet port in the centre flanked by a Mini USB port on its left, and a circular “barrel jack” on its right. 

![BeagleBone](.gitbook/assets/bb.jpg)

{% hint style="info" %}
There are two other receivers compatible with the Motus network: the SensorStation made by Cellular Tracking Technologies \(CTT\) and the SRX receivers made by Lotek. For guides on how to use these receivers, please consult CTT or Lotek respectively.
{% endhint %}

