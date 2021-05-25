---
description: >-
  You can view live detections of your project's Lotek tags on the SensorGnomes
  web interface by following these steps.
---

# Uploading a local tag database

## Introduction

If you are installing a station that detects Lotek tags, it is useful to know whether it is able to detect tags in real time. Thankfully this is possible by loading a local tag database on to the internal storage of the device. When the SensorGnome boots up, it checks for a tag database and will display any of those tags it "hears" on its web interface. 

Viewing your live tag detections can also be useful when deploying tags or as a make-shift manual tracking device when a Lotek receiver is unavailable.

This works by using a local version of the tag finder algorithm \([`find_tags_unifile`](https://github.com/MotusWTS/find_tags)\) in comparison with the tag recordings provided during registration. Note that this local version differs from the version found on Motus, mainly in that Motus only searches for tags that are known to be actively deployed during the given time period.

### Steps

1. Download the tag database from your [project's tag management pages ](http://motus.org/data/project/tags)on Motus. ![](../.gitbook/assets/download-tag-database.png) 
   * If there are multiple files to choose from, pick the last file in the list for the most recent set of tags.
2. Connect to your SensorGnome with a computer using 'root' as both the username _and_ password and navigate to the [`uboot`](https://docs.motus.org/sensorgnome/appendix/cheatsheet#uboot-folder-configuration-files)folder.
3. Rename the files `SG_tag_database.sqlite` and `SG_tag_database.csv` with the suffix ‘old’, or delete them all together.
4. Copy the tag database you just downloaded from _motus.org_ into the `uboot` folder. Rename the file to `SG_tag_database.sqlite`
5. Reboot the SensorGnome.
6. Load [the SensorGnome's web interface](../webinterface.md) and scroll down to near the bottom of the page where it says "Tag Database" and verify the list of tags includes tags from your project.

You are done! You can now view the ["live known tags" pane](../webinterface.md#pulses-and-tags-pane) at the top of the page to check whether your tags are being detected by this station.

