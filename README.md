# Somfy plugin for Domoticz
Original script was written by Nonolk : https://github.com/nonolk/domoticz_tahoma_blind.git

Special thanks to Jan-Jaap who did the rewritting of the plugin

Domoticz plugin writen in Python to first support Somfy IO roller shutters using Tahoma/Connexoon. 
Basic support of RTS (Open/Close) is also included without return state (limitation due to RTS), it means for RTS the state of the device won't be updated if the device state is modified outside of domoticz.

To use this plugin you need to install the last stable release of Domoticz https://www.domoticz.com and to install the required python library.

The plugin currently support the following device types: roller shutters, screens (interior/exterior), awning, pergolas, garage door, windows, luminance sensor and blinds(postions and slats control).

## Important note
When upgrading to version 3.x, it is required to first remove all devices attached to the Somfy hardware. This has to do with the upgrade to the Domoticz Extended Framework, which enabled the slats/orientation control for the blinds.
 The plugin will not upgrade when there are still devices attached to the Somfy hardware.

## Somfy login

You need to register you Somfy products and add them to your Tahoma or Connexoon box

https://www.somfy.nl/nieuw-account-aanmaken

https://www.tahomalink.com/enduser-mobile-web/steer-html5-client/tahoma/



## Installation
### Prerequisites
Python version 3.7 or higher required & Domoticz version 2022.1 (due to extended plugin framework) or greater. 

First, Follow the Domoticz guide on [Using Python Plugins](https://www.domoticz.com/wiki/Using_Python_plugins).

To install:
```
sudo apt-get update
sudo apt-get install python3 libpython3-dev libpython3.7-dev
sudo apt-get install python3-requests
```

Add your Somfy box Pin number to the local network in etc/hosts
```
192.168.1.1 1234-1234-1234
```
To be able to run the local test tool, also install:
```
pip3 install console-menu
```

### plugin
Then go in your Domoticz directory using a command line and open the plugins directory.
```
cd domoticz/plugins
git clone https://github.com/MadPatrick/somfy
```
Restart Domoticz with 
```
sudo systemctl restart domoticz.
```

to update:
```
cd domoticz/plugins/somfy
git pull
```

In the web UI, navigate to the Hardware page. In the hardware dropdown list there will be an entry called "Somfy Tahoma or Connexoon plugin".
