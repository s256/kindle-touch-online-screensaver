# Online Screensaver
### version 0.3, updated 2014-03-31

## Description

The Online Screensaver automatically fetches a new screensaver image from a user-specified URL at a user-specified interval. If a screensaver is shown at download time, the downloaded image will be displayed right away.

This extension supports updating the screensaver even when the Kindle is asleep (obviously it won't work if you have really powered the Kindle down by pressing the power button for many seconds). As such, it will use additional battery as it will un-suspend your Kindle at the configured intervals for one or two minutes.

The image should be in the correct resolution of your device, otherwise the results may not look so pretty :-) The image also needs to be a "clean" png, as otherwise you may only get a white screen (you can test whether an image is working by calling "eips -f -g image.png" on your Kindle).

Possible use cases:
download the latest weather report (this was the initial reason this extension was developed), you need a server to automatically create this image - see for example https://github.com/mpetroff/kindle-weather-display
download the latest comic each day as your screensaver
download inspirational images/messages each day
etc

## Disclaimer

As of version 0.1, this extension has only been tested on a Kindle Paperwhite 2 with WiFi. Support of other devices is unknown, but feedback is appreciated. How this script interacts with 3G models is also unknown. Also unknown is what happens if damaged image files are downloaded.

It is recommended to test the extension manually prior to activating auto updates. To do so, connect to your Kindle via SSH (ref. USBNet) and run

```
/mnt/us/extensions/onlinescreensaver/bin/scheduler.sh &
```
and then exit. If anything should go wrong, rebooting the Kindle should fix any problem.

Either way, as usual please be advised that you are using this extension on your own risk.


## Prerequisites
* The script requires FW5.x / Paperwhite devices
* You must have KUAL v2 or later installed.
* You must have linkss installed ("screensavers hack")
* The extension copies the screensaver image to /mnt/us/linkss/screensavers as bg_medium_ss00.png. On Paperwhite 2, you most likely already have a file of that name - if you don't want it overwritten, please make a backup. It is advisable to only have one screensaver image, as otherwise the results may become unpredictable.


## Installation

Unzip the downloaded file into the extensions folder (/mnt/us/extensions when using SSH, otherwise the extensions folder at root of the Kindle volume when connected to your PC).


## Configuration

Edit `onlinescreensaver/bin/config.sh`, all available options are described here. Note that you MUST use an editor that supports Unix line endings. On Windows, use e.g. the free notepad++ application.


## Uninstalling

It is recommended to disable auto-updates prior to deleting the folder from the extensions directory.