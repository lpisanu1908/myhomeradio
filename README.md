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


