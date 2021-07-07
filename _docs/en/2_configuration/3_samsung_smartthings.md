---
layout: docs
name: samsung-smartthings-configuration
title: Configure Samsung SmartThings third-party
category: Configuration
permalink: "/en/configuration"
lang: en
---

## Create a SmartThings account

First, you should have or create a account to acces to [Samsung SmartThings Workspace](https://smartthings.developer.samsung.com/workspace/).

## Create a project

Then, create a **new project** to bind your Gladys instance.

Select **Device Integration** as kind of new project, then **SmartThings Cloud Connetor**, and finally **SmartThings Schema Conector**.

Fill the name field with your new application name (example: _Gladys V4_).

## Configure the project

Under **Develop** menu, go to **Cloud Connector | Schema App**, and select **WebHook Endpoint**.

<img src="/assets/image/configuration/samsung-smartthings/create_webhook_endpoint.png" alt="WebHook Endpoint selection" class="img-responsive" width="600" />

Then, fill required fields:
 - Target URL - Enter external secure (HTTPS) URL of your Gladys instance (example: `https://my-gladys.com`).
 - (**Next page**)
 - Client ID - The client ID displayed on Gladys SmartThings integration page.
 - Client Secret - The client Secret displayed on Gladys SmartThings integration page.
 - Authorization URI - The authorization URL based on your external URL: `/authorize` (example: `https://my-gladys.com/authorize`)
 - Token URL - The token URL based on your external URL: `/api/v1/oauth/token` (example: `https://my-gladys.com/api/v1/oauth/token`)
 - OAuth Scope(s) - Let it empty.
 - (**Next page**)
 - App Display Name - Fill with application name **Gladys V4**.
 - Logo - Picture to identify the application, please get the [following one](#smt-gladys-logo).
 - Then **Save**.

<img src="/assets/image/configuration/samsung-smartthings/gladys_logo.png" alt="Gladys logo" class="img-responsive" width="300" id="smt-gladys-logo" />

## Publish the projet

To make it visible from your smartphone, you should activate it.
Go to **Overview** page, and **Deploy to Test**.

<img src="/assets/image/configuration/samsung-smartthings/deploy_to_test.png" alt="SmartThings credentials" class="img-responsive" width="600" />

## Configure Gladys

Once created, application credentials sould be generated and visible under **Develop** > **Cloud Connector | Schema App** menu.

<img src="/assets/image/configuration/samsung-smartthings/smartthings_credentials.png" alt="SmartThings credentials" class="img-responsive" width="600" />

Copy client ID and Secret and paste into Gladys SmartThings integraton page.

## Configure your smartphone

### Developer mode

As the created application is not the _official one_, you have to enable the developer mode on your SmartThings smartphone application.

1. Launch the SmartThings app.
2. Go to **Dashboard** > **Settings**.
<img src="/assets/image/configuration/samsung-smartthings/developer_mode_1.jpg" alt="SmartThings developer mode 1" class="img-responsive" width="600" />

3. Long-press **About SmartThings** for 5 seconds.
<img src="/assets/image/configuration/samsung-smartthings/developer_mode_2.png" alt="SmartThings developer mode 1" class="img-responsive" width="600" />

4. Enable the Developer Mode.
5. Restart the SmartThings app.

### Link Gladys application

1. Tap **Add device** on the **Dashboard** tab of the SmartThings app.
<img src="/assets/image/configuration/samsung-smartthings/add_testing_device_1.jpg" alt="SmartThings add device 1" class="img-responsive" width="600" />

2. Go to **ADD DEVICE MANUALLY** and click **My Testing Devices**. You can now see and add your self-published devices.
<img src="/assets/image/configuration/samsung-smartthings/add_testing_device_2.jpg" alt="SmartThings add device 2" class="img-responsive" width="600" />

3. Confirm the connection by selecting **ALLOW** on Gladys web page.