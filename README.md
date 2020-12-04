I had a few spare speakers at home and wanted to place them around to be able to listen to my favorite radios in whichever room I was in. I didn't want a full media system with all those smart features you can find in Kodi or Plex or the others. What I wanted was being able to choose the output speaker and listen to my radio stations.

I had a few analog speakers and a couple of bluetooth ones. My choice was to use my Raspberry. I connected my analog speakers and paired my bluetooth speakers using Bluealsa.

It is simple and it works perfectly. Also, I can stream to my phone.

INSTALL

I use Armbian but Ubuntu shoud work too.

Install lighttpd and php. I assume the root dir is the standard /var/www/html. Under it create folders conf and radio. Unzip radio.zip in the root folder. The resulting layout will be:

radio.php
common.php
  /conf/radio.json
  /radio/radio.css
  
Edit common.php to change the few configuration defines regarding your lighttpd configuration.

The file radio.json contains the few working parameters for the application:

currentradio: the name of the current streaming radio
currentvolume: 0-100
sort: show radios sorted by name
radios: an array containing radios in the form ["radioname", "radiourl"], ["radioname", "radiourl"], ["radioname", "radiourl"] ....
categories: an array containing radios grouped by categories (i.e. "UK", "Pop", "80s"...)
currentdevice: selected playing output device (speaker)
device: the object containing the parameters for operating device (speaker). See below.

DEVICES

With multiple device types I had to conceive a common method to init, start and stop output to a speaker. So a device consists of:

"name": identifies the device with a friendly name
"devicename": identifies the device with a technical name
"play": cli commands to start playing
"stop": cli commands to stop playing
"turnon": cli commands to turn on device
"turnon": cli commands to turn off device
"init": cli commands to initialize device
"setvolume": cli commands to set device volume (0-100)

The included sample works, as you can see I use mplayer but you can use whatever you wish.

