---
name: mqtt-api
title: MQTT API
permalink: "/en/api"
lang: en
category: API
---

If you configured a MQTT Broker with your Gladys installation, you have access to Gladys MQTT API.

Here are all the MQTT topics available, with examples of message to send:

#### Send Pod Heartbeat

This topic is used to tell Gladys that a pod is alive.

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

#### Declare a new Pod

This topic is useful to declare a new pod in Gladys.

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

#### Declare a new service

This topic is useful to declare a new service in Gladys.

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

#### Create a device

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

#### Push a new device state

Topic:

```
gladys/master/device/state/update
```

Example 1:

```json
{
  "device_feature_external_id": "philips-hue:1:binary",
  "state": 1
}
```

#### Receive a request to change device state

Action comes from Gladys, published over MQTT network, and should be handled by MQTT device.

Topic:

```
gladys/${feature_id}/update
```

Payload: the new device state.

Example 1:
My device feature ID is `mqtt:my_device` and changes from OFF (`0`) to ON (`1`).
Topic: `gladys/my_device/update`
Payload: `1`
