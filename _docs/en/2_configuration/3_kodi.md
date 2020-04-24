---
layout: docs
name: kodi-configuration
title: Configure Kodi devices
category: Configuration
permalink: "/en/configuration"
lang: en
---

## Configure Kodi Media Center
Before add Kodi Media Center device, ensure you have already configure Kodi to allowed 'Web Conrtrol' in settings (menu: Settings / Services / Control), like: 

<img src="/assets/image/configuration/kodi/kodi-config-en.jpg" class="img-responsive" />

## Configure device

Go to  Gladys -> Integration -> Kodi -> Devices page and you can add Kodia Media Center device with this form:

<img src="/assets/image/configuration/kodi/kodi-device-form.jpg" class="img-responsive" />

Each input text correspond to :
    Name : name of device
    Room : location in house of the device
    Default : if you have many defined device, this value specify the default device (when you don't specify a room in action)
    Parameters :
        Host : IP address or domain name of your Kodi Media Center
        Port : Port of control configured in Kodi Media Center (default: 9090)

After this configuration done you can use 'Test connection' button to check parameters before save (ensure your Kodi Media center is up).