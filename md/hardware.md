# Hardware Listing

## Table of Contents
  * [Amazon Echo](#Amazon-Echo)
  * [Shelly](#Shelly)
  * [Zigbee](#Zigbee)

### Amazon Echo

Adjust volume:
```
service: media_player.volume_set
data:
  entity_id: media_player.kitchen
  volume_level: '0.2'
```

Read some text on a specific device:
```
service: notify.alexa_media
data:
  message: Good evening, this is a test.
  data:
    type: tts
  target: media_player.kitchen
```

### Shelly 

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
| [Shelly 1 (Gen1)](https://shelly.cloud/products/shelly-1-smart-home-automation-relay/) | Light Switch | :smile: | Shelly's flagship product and it is very simple to use. This is used in several location in my automation, anywhere there is a non-dimmable paddle switch I use these relays. |

### Zigbee Devices

| Device Name | Function | Satisfaction | Notes |
| --- | --- | :---: | --- |
| [Sengled (E21-N1EA)](https://amzn.to/3irWqgP)| RGBW SMart Lights | :smile: | These are used both inside and outside of the home.  As long as the Zigbee network is stong, they work well.  These are designed specifically NOT to be Zigbee repeaters |
| [Innr (SP 224)](https://amzn.to/3it37zi)| Smart Plug/Hub | :smile: | This is a Zigbee 3.0 smart plug and repeater. Unfortunatly this does NOT provide power monitoring, but the dependability has been really good.  |
| [SONOFF Zigbee 3.0 USB Dongle](https://amzn.to/3D1yxGd) | Zigbee Gateway | :neutral_face: | This device plugs into my Home Assistant server to create and manage the Zigbee network.  Getting it to work with HA was not difficult, but I feel like the range could be better |
