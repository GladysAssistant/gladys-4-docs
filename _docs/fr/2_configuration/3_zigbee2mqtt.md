---
layout: docs
name: zigbee2mqtt-configuration
title: Configurer les périphériques Zigbee2mqtt
category: Configuration
permalink: "/fr/configuration"
lang: fr
---

## Lien officiel

Rendez-vous sur le site officiel: [zigbee2mqtt.io](https://www.zigbee2mqtt.io/).

## Dongle Zigbee

### Clé en main

Demandez à votre moteur de recherche préféré pour acheter un dongle CC2531 avec `Z-Stack-firmware`, ou rendez-vous sur le [forum de la communauté Gladys](https://community.gladysassistant.com/t/v4-integration-zigbee2mqtt/5009/6).

### Faites le vous-même (DIY)

#### Matériel requis

- CC253X USB Dongle
- CC Debugger

#### Flash Firmware

1. Connectez le dongle Zigbee sur le module CC Debugger, et le module CC Debugger sur votre ordinateur.
   - La LED verte doit être allumée.
   - Si ce n'est pas le cas, inversez le sens du câble sur le dongle Zigbee. Pas de panique, cela n'endommagera pas votre matériel.
<img src="/assets/image/configuration/zigbee2mqtt/plug_CC-debugger.jpg" alt="Flash" class="img-responsive" width="600" />

2. Téléchargez, installez et exéctuez le logiciel [SmartRF Flash Programmer](http://www.ti.com/tool/flash-programmer) (pas la V2).
3. Téléchargez et selectionnez le firmware [CC2531_DEFAULT_20190608.zip](https://github.com/Koenkk/Z-Stack-firmware/raw/master/coordinator/Z-Stack_Home_1.2/bin/default/CC2531_DEFAULT_20190608.zip).
4. `Erase, program and Verify` et `Perform actions`.
<img src="/assets/image/configuration/zigbee2mqtt/SmartRF_Flash.jpg" alt="Flash" class="img-responsive" width="600" />

5. Félicitations, vous possédez un dongle **Zigbee2mqtt**.

## Configurer avec MQTT

Créez un nouveau fichier de configuration dans le répertoire dédié à Zigbee2mqtt :
```sh
mkdir -p zigbee2mqtt/data
nano zigbee2mqtt/data/configuration.yaml
```

Copiez et collez la configuration suivante, en prennant soin d'adpater les variables `$MQTT_SERVER`, `$MQTT_USER` et `$MQTT_PASSWORD` à votre cas :
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

## Démarrer dans Docker

Exécutez simplement la commande suivante pour démarrer le programme Zigbee2mqtt dans un conteneur Docker :
```sh
docker run -d \
  --restart=always \
  --network=gladys-net \
  --name zigbee2mqtt \
  -v ${PWD}/zigbee2mqtt/data:/app/data \
  --device=/dev/ttyACM0:/dev/ttyACM0 \
  koenkk/zigbee2mqtt
```

Remplacez la valeur `/dev/ttyACM0` sur la ligne `--device=/dev/ttyACM0:/dev/ttyACM0` selon l'interface utilisée par votre dongle Zigbee2mqtt.

## Intégration dans Gladys

Dans un premier, assurez vous que Gladys est bien configuré votre votre broker MQTT.
Puis, rendez-vous sur la page d'intégration Zigbee2mqtt, cliquez sur le menu `Découvrir` et vos périphériques Zigbee vous attendent.
