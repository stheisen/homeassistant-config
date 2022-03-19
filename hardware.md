# Hardware Listing

# Shelly 

Shelly's devices use WiFi which really increases the range that these devices function. The best part is they
operate without or (in my case) without dependancy on the cloud.  All of the shelly devices are added to the 
system directly using [HA's core Shelly support](https://www.home-assistant.io/integrations/shelly/).

Adding the devices without the use of the shelly app is a snap. Just join the wifi network that it creates once
it is powered on, typically named "Shelly-XXXXXX".  Open a browser on the joined device and navigate to http://192.168.33.1.
From there the device can be joined to the home WIFI network.  Be sure to jump on the router and assign each of
the Shelly devices a static IP address. Log into HA, and add a Shelly integration.  Enter the static IP address 
assigned to the device when prompted, and the device is prepared for automation. 

I will use the table below to document the devices used on my automation, and some notes about my experience with them.

| Device Name | Function | Satisfaction | Notes |
| --- | --- | :---: | --- |
| [Shelly 1](https://shelly.cloud/products/shelly-1-smart-home-automation-relay/) | Light Switch | :heavy_check_mark: | Shelly's flagship product and it is very simple to use. This is used in several location in my automation, anywhere there is a non-dimmable paddle switch I use these relays. |

# Zigbee Devices

