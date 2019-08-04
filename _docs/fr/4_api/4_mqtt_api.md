---
name: mqtt-api
title: MQTT API
permalink: "/fr/api"
lang: fr
category: API
---

Si vous avez configurer un broker MQTT avec Gladys, vous pouvez communiquer avec Gladys via MQTT.

#### Pod Heartbeat

Pour dire à Gladys qu'un bot est toujours en ligne.

Topic:

```
/gladys/master/heartbeat
```

Body:

```json
{
  "pod_selector": "raspberry-pi-zero-pod"
}
```

#### Déclarer un nouveau pod

Pour créer un nouveau pod dans Gladys:

Topic

```
/gladys/master/pod/create
```

Body:

```json
{
  "name": "Raspberry Pi Zero Pod",
  "selector": "raspberry-pi-zero-pod"
}
```

#### Déclarer un nouveau service

Pour créer un service distant dans Gladys:

Topic

```
/gladys/master/service/create
```

Body:

```json
{
  "name": "Voice Recognition Service",
  "selector": "voice-recognition-service",
  "pod_id": "42c78884-af53-4514-974a-136fe07bd9e7",
  "version": "1.0.0",
  "has_message_feature": true
}
```

#### Créer un périphérique

Topic

```
/gladys/master/device/create
```

Body:

```json
{
  "name": "New Lamp",
  "external_id": "philips-hue:1",
  "should_poll": false,
  "features": [
    {
      "name": "On/Off",
      "category": "light",
      "type": "binary",
      "read_only": false,
      "has_feedback": false,
      "min": 0,
      "max": 1
    }
  ]
}
```

#### Envoyer un nouvel état de périphérique

Topic:

```
/gladys/device/state/new
```

Example 1:

```json
{
  "device_feature_external_id": "philips-hue:1:binary",
  "state": 1
}
```

Example 2:

```json
{
  "device_external_id": "philips-hue:1",
  "category": "light",
  "type": "binary",
  "state": 1
}

```

#### Envoyer un nouvel état de périphérique (compatibilité V3)

Cette partie permet de conserver la compatibilité des périphériques MQTT créé pour Gladys V3.

Topic:
```
/gladys/device/devicestate/new
```

Example 1:
```json
{
  "identifier": "philips-hue:1"
  "type": "binary",
  "state": {
    "value": 1
  }
}
```
