---
description: >-
  Underpowered SensorGnomes are a potential issue with off-grid stations which
  can seem confusing at first. If your SensorGnome has signs of being
  underpowered, it should be addressed to ensure station
---

# Underpowered SensorGnomes

## What is an underpowered SensorGnome?

When a SensorGnome isn't receiving enough power -- that is, the voltage and/or current is lower than the device is rated for -- it can result in a malfunctioning station that doesn't collect data.&#x20;

This typically occurs in off-grid stations due to the non-standard power supply that is used; however, this is also possible if an incorrect AC adaptor is used. The AC adaptor should output 5.1 Volts and 2.5 Amps (2500 mA).

Raspberry Pi based SensorGnomes in off-grid setups are most susceptible to underpowered situations due to the higher voltage requirements in comparison to BeagleBone computers (5.1 V required for Raspberry Pi; 5.0 for BeagleBone). The DC-DC voltage converter used in the SensorGnome, which converts the batteries 12 Volts down to something the computer can use, outputs just 5.0 Volts and 2.0 Amps. This alone isn't enough for the SenorGnome to malfunction, but over time wear and tear to the USB cable and its connections can increase the resistance to the flow of electricity and can eventually result in a malfunctioning system.

### How does it occur?

It most cases, general wear and tear triggers the problem. This is because the USB cables experience a fair bit of strain over their lifetime from repeated bending. The following problems have been identified at Motus stations in the past:&#x20;

* The connection to the screw terminals on the DC-DC voltage converter is loose
* Individual copper strands within the USB cable are broken. This can occur from repeated bending of the cable.
* The microUSB port of the Raspberry Pi is damaged (lifts from the circuit board slightly when force is applied).

## Identifying an underpowered SensorGnome

The behaviour of underpowered devices can be inconsistent and hard to diagnose. In most cases, it is not possible to connect to the device because both Ethernet and Wi-Fi are malfunctioning, however it may still appear as though the device is on as the indicator LEDs will be blinking. This can also be due to corrupted data on the SD card or a physical connection problem with the SD card, so it's not always obvious.&#x20;

{% hint style="info" %}
In our experience, it's always best to have a complete spare SensorGnome available so that components can be swapped out and tested.&#x20;
{% endhint %}

When trying to connect to Wi-Fi, there are a few different reasons why it may not work:

* Button never lights up
* Button lights up, but no Wi-Fi network is visible
* Wi-Fi network is visible, but can't connect to it

If swapping out the computer _and _Wi-Fi button (if applicable) doesn't change the behaviour, it's likely it is an underpowered SensorGnome and the issue lies with the power supply/USB Cable.

{% hint style="warning" %}
Sometimes the above symptoms are intermittent and during apparently random intervals it's possible to connect to the SensorGnome. This should still be considered an underpowered device since it's likely a slight shift in the USB cable's position which is causing this unpredictable behaviour.
{% endhint %}

{% hint style="info" %}
While it might seem like it's helpful to use a voltmeter to determine whether the power supply is the issue, it's often that the USB cable is the culprit which hard to measure.
{% endhint %}

## Fixing power supply issues

{% hint style="warning" %}
Always keep a spare micro USB cable handy, one that has at least 22 gauge power delivery. See [USB Micro B Male cables for power delivery](underpowered-sensorgnomes.md#usb-micro-b-male-cables-for-power-delivery).&#x20;
{% endhint %}

In most cases, fixing the issue is as simple as replacing the Micro USB cable which plugs into the Raspberry Pi. It is also possible to swap out the DC-DC voltage converter to a device that is rated for more current and/or voltage (no more than 5.1 V, however!), but these have not been tested. See: [DC-DC Voltage Converters for Raspberry Pi (not tested)](underpowered-sensorgnomes.md#dc-dc-voltage-converters-for-raspberry-pi-not-tested).

### USB Micro B Male cables for power delivery

Currently available (as of Nov 3, 2021) cables are listed below:

| Retailer  | Price              | Gauge  | Link                                                                                        |
| --------- | ------------------ | ------ | ------------------------------------------------------------------------------------------- |
| DigiKey   | $6.21 CAD          | 20 AWG | [Product page](https://www.digikey.ca/en/products/detail/tripp-lite/UR05C-003-UARB/5359414) |
| MonoPrice | $0.99 USD (0.5 ft) | 22 AWG | [Product page](https://www.monoprice.com/product?p\_id=13924)                               |

### DC-DC Voltage Converters for Raspberry Pi (not tested)

Currently available (as of Nov 3, 2021) DC-DC converters are listed below. Please note that these models have not been tested, but are expected to perform better the default model.

| Retailer | Price     | Volts (V) | Watts (W) | Link                                                                                       |
| -------- | --------- | --------- | --------- | ------------------------------------------------------------------------------------------ |
| DigiKey  | $60 USD   | 5.1 V     | 20 W      | [Product page](https://www.digikey.ca/en/products/detail/xp-power/DTE2024S5V1/5931159)     |
| DigiKey  | $38.5 USD | 5.0 V     | 20 W      | [Product page](https://www.monoprice.com/product?p\_id=13924)                              |
| DigiKey  | $51 USD   | 5.1 V     | 10 W      | [Product page](https://www.digikey.ca/en/products/detail/traco-power/TMDC-10-2411/9698249) |
