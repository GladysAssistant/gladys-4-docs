---
layout: docs
name: zigbee2mqtt-configuration
title: Configure Zigbee2mqtt devices
category: Configuration
permalink: "/en/configuration"
lang: en
---

## Official link

Please refer to official Zigbee2mqtt web site: [zigbee2mqtt.io](https://www.zigbee2mqtt.io/).

## Zigbee device key

### Ready to use

Ask your favorite search engine to buy a CC2531 dongle with `Z-Stack-firmware`, or look at [Gladys community forum](https://community.gladysassistant.com/t/v4-integration-zigbee2mqtt/5009/6).

### Do it yourself

#### Required device

- CC253X USB Dongle
- CC Debugger

#### Firmware flashing


1. Plug Zigbee dongle on the CC Debugger module, and CC Debugger on your computer.
   - Green LED should be ON.
   - If not, reverse the Zibgee cable. Don't worry, it won't damage your dongle.
<img src="/assets/image/configuration/zigbee2mqtt/plug_CC-debugger.jpg" alt="Flash" class="img-responsive" width="600" />

2. Download, install and run [SmartRF Flash Programmer](http://www.ti.com/tool/flash-programmer) (not V2) software.
3. Dowload and select [CC2531_DEFAULT_20190608.zip](https://github.com/Koenkk/Z-Stack-firmware/raw/master/coordinator/Z-Stack_Home_1.2/bin/default/CC2531_DEFAULT_20190608.zip) firmware.
4. `Erase, program and Verify` and `Perform actions`.
<img src="/assets/image/configuration/zigbee2mqtt/SmartRF_Flash.jpg" alt="Flash" class="img-responsive" width="600" />

5. Congratulations, you now have a **Zigbee2mqtt** dongle.

## Configure with MQTT broker

Create a new configuration file in the dedicated Zigbee2mqtt directory: 
```sh
mkdir -p zigbee2mqtt/data
nano zigbee2mqtt/data/configuration.yaml
```

And paste following configuration, according to your local `$MQTT_SERVER`, `$MQTT_USER` and `$MQTT_PASSWORD`:
```yaml
homeassistant: false
permit_join: true
mqtt:
  base_topic: zigbee2mqtt
  server: '$MQTT_SERVER'
  user: $MQTT_USER
  password: $MQTT_PASSWORD
serial:
  port: /dev/ttyACM0
```

## Start in Docker

Simply run following docker container:
```sh
docker run -d \
  --restart=always \
  --network=gladys-net \
  --name zigbee2mqtt \
  -v ${PWD}/zigbee2mqtt/data:/app/data \
  --device=/dev/ttyACM0:/dev/ttyACM0 \
  koenkk/zigbee2mqtt
```

Replace `/dev/ttyACM0` value on `--device=/dev/ttyACM0:/dev/ttyACM0` line according the USB interface used by the Zigbee2mqtt key.

## Gladys integration

First, be sure you well configure the MQTT service with your current MQTT broker.
Then, go to Zigbee2mqtt integration page, and click on `Discover` to bind Zigbee devices to Gladys.
