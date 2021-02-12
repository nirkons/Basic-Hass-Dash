# (Very) Basic Home Assistant Control Dashboard

![Pic](https://user-images.githubusercontent.com/24681877/43090528-467e10d4-8eb0-11e8-86ad-47764cf078e1.jpg)

Discussion:
https://community.home-assistant.io/t/very-basic-homeassistant-dashboard-for-e-ink-devices-and-kiosk-apps/61002

Notice: This repo is not actively maintained, but has been updated at the beginning of 2021 to support the latest API with long lived token

This basic HA dashboard is great for E-ink devices with a browser going as far back as the Kindle 2 (using Advanced mode browser), and also for all the Kiosk browsers on the Play store/App store that fail to run the original HomeAssistant dashboard.

There are 2 types of dashboards at your disposal:
  - Manual local dashboard  - Use this template and edit/add your own table cells on your own and set only the specific devices you want (including Sensors)

  - Automatic local dashboard - Gets all your HomeAssistant devices automatically (disregards Groups, Sensors, Automations, Scripts, Update notifications and Persistant Notifications).

### Installation & Configuration
For all dashboards, you will need to add in the http module in your HomeAssistant configuration.yaml

~~~~
cors_allowed_origins:
  - 'null'
~~~~
 
(Or if you are uploading to a webserver, replace null with the webserver address)
Don't forget to restart your HA server for this new setting to work.


1. For Manual Local - 
Open the HTML file in any text editor and fill in your HomeAssistant address in hassadress and Long Lived access token in hasspass (Note there are 3 places to fill this in), you can get a long lived token through your user's profile page in HomeAssistant.
    Scroll down to the HTML code and change the button ids to match your entity ids from your own homeassistant installation.
    Finally, upload it directly to your e-ink device or to a webserver (if you are uploading online, make sure you are protecting this with a password), For Kindle devices, upload to either your root directory or a folder, open the experimental browser and go to
file:///mnt/us/FOLDER/ManualLOCAL.html
(Replace "FOLDER" with the folder you created or remove it if you uploaded to root directory)

2. For Automatic Local - 
    Open the HTML file in any text editor and fill in your HomeAssistant address in hassadress and Long Lived access token in hasspass (Note there are 2 places to fill this in), you can get a long lived token through your user's profile page in HomeAssistant.
    if you have a media player other than Spotify, change the id from media_player.spotify under where it says "SET YOUR MEDIA PLAYER HERE"
    Finally, upload it directly to your e-ink device or to a webserver (if you are uploading online, make sure you are protecting this with a password), For Kindle devices, upload to either your root directory or a folder, open the experimental browser and go to
file:///mnt/us/FOLDER/AutomaticLOCAL.html
(Replace "FOLDER" with the folder you created or remove it if you uploaded to root directory)

### Misc
You can disable the screensaver/sleep mode in your Kindle 

Newer kindles (2015 Paperwhite & up)
type ~ds in the search bar and click search.
(Don't worry, After restarting the Kindle the screensaver will return)

Older Kindles:
Type ~disableScreensaver in the search box (type del on the home screen) and your Kindle will not go into sleep mode. ~resumeScreensaver will revert the Kindle back to its default (screensaver enabled) state. Note that this does not increase power consumption, as the Kindle consumes no power (with wireless off) when displaying a page

Or < Del > to open the search box on the home screen ;debugOn <Enter> ~disableScreensaver <Enter>
NOTE: this also stops you from manually using the power switch to enter sleep mode.
To re-enable: ~resumeScreensaver <Enter> and to turn off debug mode: ;debugOff <Enter>



