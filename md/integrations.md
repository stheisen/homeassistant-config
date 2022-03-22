[Home](https://github.com/stheisen/homeassistant-config)
# Integration Details

## Table of Contents
  * [HACS](#HACS)
    * [Alexa Media Player](#Alexa-Media-Player)

### HACS
Although some want to avoid it, there comes a time when the core of Home Assistant can't provide all the needs of your desired automation. 
The first place most automators turn to is the Home Assistant Community Store ([HACS](https://hacs.xyz/)).
After following the download and configration steps listed on the [HACS website](https://hacs.xyz/), I added the following HACS integrations below.

### Alexa Media Player
If you have a pile of Echos spread around your house, then the [Alexa Media Player](https://github.com/custom-components/alexa_media_player) HACS integration 
is a great choice to get text-to-speech notifications from them **for free**.  Getting the integration up an running via 2FA was a bit challenging, so 
make sure to follow the [Installation and Configuration](https://github.com/custom-components/alexa_media_player/wiki/Configuration) documentation closely.

#### Service Examples
Adjust the volume of devices:
```
service: media_player.volume_set
data:
  entity_id: media_player.kitchen, media_player.garage
  volume_level: '0.2'
```

Read text on devices:
```
service: notify.alexa_media
data:
  message: Good evening, this is a test.
  data:
    type: tts
  target: media_player.kitchen, media_player.garage
```