# (Very) Basic Home Assistant Control Dashboard

![Pic](https://user-images.githubusercontent.com/24681877/43090528-467e10d4-8eb0-11e8-86ad-47764cf078e1.jpg)

This basic HA dashboard is great for E-ink devices with a browser going as far back as the Kindle 2 (using Advanced mode browser), and also for all the Kiosk browsers on the Play store/App store that fail to run the original HomeAssistant dashboard.

There are four types of dashboards at your disposal split into two categories: Local (A Homeassistant installation which is NOT exposed to the internet and does not use an SSL certificate) and Cloud (A homeassistant installation that is exposed and is using a domain name with an SSL certificate).
  - Manual local dashboard  - Use this template and edit/add your own table cells on your own and set only the specific devices you want (including Sensors)

  - Automatic local dashboard - Gets all your HomeAssistant devices automatically (disregards Groups, Sensors, Automations, Scripts, Update notifications and Persistant Notifications).

- Manual cloud dashboard - Use this template and edit/add your own table cells on your own and set only the specific devices you want (including Sensors) using your exposed installation and Integromat (free tier)

- Automatic cloud dashboard - Gets all your HomeAssistant devices automatically (disregards Groups, Sensors, Automations, Scripts, Update notifications and Persistant Notifications) using your exposed installation and Integromat (free tier)

### Installation & Configuration
1. For Manual Local - 
Open the HTML file in any text editor and fill in your HomeAssistant address in hassadress and password in hasspass (Note there are 3 places to fill this in)
    Scroll down to the HTML code and change the button ids to match your entity ids from your own homeassistant installation.
    Finally, upload it directly to your e-ink device or to a webserver (if you are uploading online, make sure you are protecting this with a password), For Kindle devices, upload to either your root directory or a folder, open the experimental browser and go to
file:///mnt/us/FOLDER/ManualLOCAL.html
(Replace "FOLDER" with the folder you created or remove it if you uploaded to root directory)

2. For Automatic Local - 
    Open the HTML file in any text editor and fill in your HomeAssistant address in hassadress and password in hasspass (Note there are 2 places to fill this in)
    if you have a media player other than Spotify, change the id from media_player.spotify under where it says "SET YOUR MEDIA PLAYER HERE"
    Finally, upload it directly to your e-ink device or to a webserver (if you are uploading online, make sure you are protecting this with a password), For Kindle devices, upload to either your root directory or a folder, open the experimental browser and go to
file:///mnt/us/FOLDER/AutomaticLOCAL.html
(Replace "FOLDER" with the folder you created or remove it if you uploaded to root directory)

3. For Manual Cloud - 
Open the HTML file in any text editor and fill in your HomeAssistant password in hasspass (Note there are 3 places to fill this in), save.
Register for a free account at https://www.integromat.com
Go to "Scenarios" and "Create a new scenario", if promted with an integration list click "Skip". On the bottom menu click the three dots and select "Import blueprint", select the Action.json file from the Integromat Manual Cloud folder in this repository. Click on the Webhook module, Add, and give it a name.
Now Integromat will want example data, open the HTML file in an editor and fill in the Webhook URL you got from Integromat, save it, open the HTML file in a browser and click some button, once we do that the webhook should be configured. Next, click on the HTTP module and change "YOUR_HASS_URL:PORT" to your real homeassistant installation URL, click OK, hit Save on the bottom left, and turn this integration on (buttom left slider).

    (For Sensors) go to Scenarios again and create another scenario, On the bottom menu click the three dots and select "Import blueprint", select the Sensors.json file from the Integromat Manual Cloud folder in this repository. Click on Webhook, Add, and give it a name. Again, Integromat will want example data, which we can provide simply by opening the HTML file again after filling in "sensorwebhookurl" with the new webhook url we got from this scenario. Again click the HTTP module and change "YOUR_HASS_URL:PORT" to your real homeassistant installation URL, click OK, hit Save on the bottom left, and turn this integration on (buttom left slider).

    Go back to the HTML file, scroll down the code and change the button ids to match your entity ids from your own HomeAssistant installation, you can add additional buttons or remove exccess buttons as you wish.
    Finally, upload it directly to your e-ink device or to a webserver (if you are uploading online, make sure you are protecting this with a password), For Kindle devices, upload to either your root directory or a folder, open the experimental browser and go to
file:///mnt/us/FOLDER/ManualCLOUD.html
(Replace "FOLDER" with the folder you created or remove it if you uploaded to root directory)

4. For Automatic Cloud
Register for a free account at https://www.integromat.com
Go to "Scenarios" and "Create a new scenario", if promted with an integration list click "Skip". On the bottom menu click the three dots and select "Import blueprint", select the Generate.json file from the Integromat Automatic Cloud folder in this repository. Click on the Webhook module, Add, and give it a name.
Now Integromat will want example data, open the HTML file in an editor and fill in the Webhook URL you got from Integromat and the homeassistant password in "hasspass", save it, and open the HTML file in a browser, once that is done the webhook should be configured. Next, click on the HTTP module and change "YOUR_HASS_URL:PORT" to your real homeassistant installation URL, click OK, hit Save on the bottom left, and turn this integration on (buttom left slider).
Now when the HTML file is opened, the table should auto-populate with your homeassistant devices.
Go to Scenarios again and create another scenario, On the bottom menu click the three dots and select "Import blueprint", select the Action.json file from the Integromat Automatic Cloud folder in this repository. Click on Webhook, Add, and give it a name. Again, Integromat will want example data, fill in the new webhook URL in "webhookactionurl" and the password in "hasspass" and save the file. Open the HTML file again and click some button, the webhook should be configured.
Again click the HTTP module and change "YOUR_HASS_URL:PORT" to your real homeassistant installation URL, click OK, hit Save on the bottom left, and turn this integration on (buttom left slider).
    Finally, upload it directly to your e-ink device or to a webserver (if you are uploading online, make sure you are protecting this with a password), For Kindle devices, upload to either your root directory or a folder, open the experimental browser and go to
file:///mnt/us/FOLDER/ManualCLOUD.html
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



