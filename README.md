# HASS-TTS-Template 1.0
Create and send TTS messages from Home Assistant

## Description
Designed for and tested with Home Assistant hassio version 0.103.5

Create TTS messages and send to designated media-players

 #### Functions:

Its created as a [Home Assistant package](https://home-assistant.io/docs/configuration/packages/)

* Set vol on the mediaplayer(s) before sending the TTS
* Pick witch media-players that should recive the TTS
* 4 TTS messages that can be edited to your likeing
* Send your TTS to the enabled media-player with the set vol. by pressing the assosiated button/script

## Screenshot from HASS GUI
<img src="https://github.com/Gnaget2/Hass-TTS.Template/blob/master/tts.png" alt="Screenshot" />

## Lovelace setup example

```yaml
cards:
  - entities:
      - input_number.tts_volum
      - input_boolean.sovrum
      - input_boolean.allrum
      - input_boolean.vardagsrum
      - input_text.tts1
      - input_text.tts2
      - input_text.tts3
      - input_text.tts4
    show_header_toggle: false
    title: TTS
    type: entities
  - cards:
      - entity: script.tts1_on
        hold_action:
          action: none
        icon: 'mdi:cast-audio'
        name: TTS 1
        show_icon: true
        show_name: true
        tap_action:
          action: call-service
          service: script.tts1_on
        type: entity-button
      - entity: script.tts2_on
        hold_action:
          action: none
        icon: 'mdi:cast-audio'
        name: TTS 2
        show_icon: true
        show_name: true
        tap_action:
          action: call-service
          service: script.tts2_on
        type: entity-button
      - entity: script.tts3_on
        hold_action:
          action: none
        icon: 'mdi:cast-audio'
        name: TTS 3
        show_icon: true
        show_name: true
        tap_action:
          action: call-service
          service: script.tts3_on
        type: entity-button
      - entity: script.tts4_on
        hold_action:
          action: none
        icon: 'mdi:cast-audio'
        name: TTS 4
        show_icon: true
        show_name: true
        tap_action:
          action: call-service
          service: script.tts4_on
        type: entity-button
    type: horizontal-stack
type: vertical-stack
```

