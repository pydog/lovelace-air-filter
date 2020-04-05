# Add lovelace card for xiaomi air purifier 2s

## How to install (Base on Home Assistant 0.107.7)
+ Add xiaomi air purifier to HA
```
fan:
  - platform: xiaomi_miio
    name: Xiaomi Air Purifier 2S
    host: 192.168.1.xxx
    token: xxxxxxxx
```
+ If you don't install HACS, you could clone to www directory in the same path of configuration.yaml
`git clone git@github.com:pydog/lovelace-air-filter.git www/community/air-filter`

+ Add the following configure in configuration.yaml
```
lovelace:
  mode: yaml

  resources:
    # Following configure for the js of xiaomi air purifier
    - url: /hacsfiles/lovelace-air-filter/air-filter.js
      type: js
```
+ Add the following configure in the ui-lovelace.yaml (It is the same path as configuration.yaml,  created if it doesn't exist)
```
title: Easy Home
views:
  - path: default_view
    title: Home
    cards:
      # Following entity for xiaomi air purifier
      - type: 'custom:air-filter'
        entity: fan.xiaomi_miio_device
```
