# allsky_weather
Adaption of the DanielGallo-script for TJ-Allsky. 

I wanted to use the script of Daniel Gallo [https://github.com/DanielGallo/AllSkyWeather]  for the overlay section in my allsky-installation.

For that I defined my own variable. I called it DS_WETTER.

My new script index-ds.js creates a json-file with the structur:

    {"DS_WETTER": {  "value": "

    --- Data from the original DanielGallo script with some modification : always \n at the EndOfLines

    "}}

I use crontab to start every 5 minutes the script
    */5 * * * * /usr/bin/node /home/pi/AllSkyWeather-main/index_ds.js s --output=/home/pi/allsky/config/overlay/extra/weatherds.json --key=xxxxxxxxxxxxxxxxxxx --city=Dresden --region=Europe/Berlin

For using node I followed the instructions of Daniel Gallo. 

With this file in the extra-file-directory ~/allsky/config/overlay/extra/
I can use the variable DS_WETTER in the overlay-editor.

# Some problems with defining the variable DS_WETTER
 - in the variable manager
 - in the file userfields.json in overlay/config
   
       {
        "data": [
        {   "id": 100,
            "name": "${DS_WETTER}",
            "description": "DD Wetter",
            "format": "",
            "sample": "WetterDATE",
            "type": "Text",
            "source": "My"
        }
       ]
          }


# The image of allsky looks like:

![image](https://github.com/dilsg/allsky_weather/assets/52743419/9134fa32-bc6e-4a83-b537-84fa6a871fe8)



