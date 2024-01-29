---
description: >-
  You can view live detections of your project's Lotek tags on the SensorGnomes
  web interface by following these steps.
---

# Uploading a local tag database

## Introduction

If you are installing a SensorGnome that detects Lotek tags, it is often useful to know whether it is able to detect tags in real time, particularly if you are deploying tags in the vicinity. Thankfully this is possible by loading a local tag database on to the internal storage of the device. When the SensorGnome boots up, it checks for a tag database and will display any of those tags it "hears" on its web interface.&#x20;

Viewing your live tag detections can also be useful when deploying tags or as a make-shift manual tracking device when a Lotek receiver is unavailable.

{% hint style="warning" %}
It's important to remember the limitations of this method: it will only search for the tags that it has been provided, and it is incapable of discerning or handling ambiguous tag IDs.
{% endhint %}

This works by using a local version of the tag finder algorithm ([`find_tags_unifile`](https://github.com/MotusWTS/find\_tags)) in comparison with the tag recordings provided during registration. Note that this local version differs from the version found on Motus, mainly in that Motus searches for tags from all projects across the network (but only those known to be actively deployed during the given time period) whereas this method will only compare raw radio data with the tag patterns it has been provided, regardless of deployment period.

{% hint style="info" %}
Loading a Lotek tag database is not yet possible on a SensorStation
{% endhint %}

### Steps

1. Navigate to your project's [Manage Tags](https://motus.org/data/project/tags) page and click on the "Download tag database" button on the right hand side
2. Download the `.sqlite` tag database. The first link contains all tags currently registered to this project, whereas the links below are older format that summarized by yearly quarter. In nearly all cases you will want the first link.
3. [Connect to your SensorGnome](../connecting.md) with a computer using 'root' as both the username _and_ password and navigate to the [`uboot`](https://docs.motus.org/sensorgnome/appendix/cheatsheet#uboot-folder-configuration-files) folder. If using the V2 SensorGnome software, you can simply upload this via the web UI.
4. Rename the files `SG_tag_database.sqlite` with the suffix ‘old’, or delete them all together.
5. Copy the tag database you just downloaded from _motus.org_ into the `uboot` folder. Rename the file to `SG_tag_database.sqlite`
6. 5\. Reboot the SensorGnome.
7. 6\. Load [the SensorGnome's web interface](../webinterface.md) and scroll down to near the bottom of the page where it says "Tag Database" and verify the list of tags includes tags from your project.

You are done! You can now view the ["live known tags" pane](../webinterface.md#pulses-and-tags-pane) at the top of the page to check whether your tags are being detected by this station.

## Merging multiple tag databases into one

As only one tag database can be loaded onto a SensorGnome at any given time, it is sometimes necessary to merge multiple tag databases together.  You can use or modify the script below to merge multiple databases in R.

```
### merge tag databases ####
# This function accepts a vector of file names 
# corresponding to the various tag databases to be merged. 
# It saves one tag database containing all the source dbs
# named 'SG_tag_database.sqlite' for copying onto a SG
# It also returns a data frame with the results for visual overview

merge_dbs <- function(db_list, out_db = 'SG_tag_database.sqlite'){
  library(RSQLite)
  
  out_df <- data.frame()
  
  # loop through the list of tag dbs to be merged
  for (i in db_list) {
    message('Processing ', i)
    # establish SQLite connection to the current tag database
    con <- dbConnect(SQLite(), i)
    # select all from the tags table of the tag database, as a data frame
    df <- dbGetQuery(con, 'SELECT * FROM tags')
    # bind (append) the resulting rows to the consolidated out_df data frame
    out_df <- rbind(out_df, df)
    # disconnect from the source tag database
    dbDisconnect(con)
  }
  
  # open a SQLite connection to your output file
  outdb <- dbConnect(SQLite(), out_db)
  # write the results to the new consolidated tag database
  # This will overwrite any existing SG_tag_database.sqlite file 
  # if one already exists in the target directory
  dbWriteTable(outdb, 'tags', out_df, overwrite = T)
  # close the connection to the new consolidated tag database
  dbDisconnect(outdb)
  
  message(length(db_list), " tag sqlite files merged into ", out_db)
  
  return(out_df)
}

# An example of how to use this function...
# Call the function and pass in the paths of the tag databases to be merged.
merged_db <- merge_dbs(c('D:/Downloads/project_322_2020-2_tag_database.sqlite',
                         'D:/Downloads/project_322_2021-2_tag_database.sqlite'))

View(merged_db)
```
