# Integration Details

# Table of Contents
  * [HACS](#HACS)
    * Alexa Media Player (#Alexa-Media-Player)

# HACS

## Alexa Media Player

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