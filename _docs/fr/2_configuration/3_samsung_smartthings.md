---
layout: docs
name: samsung-smartthings-configuration
title: Configurer l'application Samsung SmartThings
category: Configuration
permalink: "/fr/configuration"
lang: fr
---

## Créer un compte SmartThings

Vous devez avoir un compte pour accéder au [Samsung SmartThings Workspace](https://smartthings.developer.samsung.com/workspace/).

## Créer un projet

Ensuite, créez un **nouveau projet** pour lier votre application Gladys.

Sélectionnez **Device Integration** comme type de nouveau projet, puis **SmartThings Cloud Connetor**, et enfin **SmartThings Schema Conector**.

Entrez le nom de l'application (exemple: _Gladys V4_).

## Configurer le projet

Sous le menu **Develop**, accédez à **Cloud Connector | Schema App**, puis sélectionner **WebHook Endpoint**.

<img src="/assets/image/configuration/samsung-smartthings/create_webhook_endpoint.png" alt="WebHook Endpoint selection" class="img-responsive" width="600" />

Puis remplissez les informations demandées :
 - Target URL - Entrez l'URL externe sécurisée (HTTPS) de votre instance Gladys (exemple : `https://my-gladys.com`).
 - (**Page suivante**)
 - Client ID - Le client ID affiché sur la page d'intégration SmartThings de votre Gladys.
 - Client Secret - Le client Secret affiché sur la page d'intégration SmartThings de votre Gladys.
 - Authorization URI - L'URL d'autorisation basée sur votre URL externe : `/authorize` (exemple : `https://my-gladys.com/authorize`)
 - Token URL - L'URL de jeton basée sur votre URL externe : `/api/v1/oauth/token` (exemple : `https://my-gladys.com/api/v1/oauth/token`)
 - OAuth Scope(s) - Laissez vide.
 - (**Page suivante**)
 - App Display Name - Remplssiez le champ avec le nom de l'application **Gladys V4**.
 - Logo - L'image poir identifier l'application Gladys, utilisez [l'image suivante](#smt-gladys-logo).
 - Puis **Save**.

<img src="/assets/image/configuration/samsung-smartthings/gladys_logo.png" alt="Gladys logo" class="img-responsive" width="300" id="smt-gladys-logo" />

## Publier le projet

Afin de rendre l'application visible sur votre smartphone, vous devez l'activer.
Rendez vous sur la page **Overview**, puis **Deploy to Test**.

<img src="/assets/image/configuration/samsung-smartthings/deploy_to_test.png" alt="SmartThings credentials" class="img-responsive" width="600" />

## Configurer Gladys

Une fois le projet créé, les informations d'identifications sont générées et visibles sur depuis le menu **Develop** > **Cloud Connector | Schema App**.

<img src="/assets/image/configuration/samsung-smartthings/smartthings_credentials.png" alt="SmartThings credentials" class="img-responsive" width="600" />

Copiez le Client ID et le Client Secret et collez les sur la page d'intégration SmartThings de votre Gladys.

## Configurer votre smartphone

### Mode développeur

Vu que l'application que vous venez de créer n'est pas une _application officielle_, vous devez activer le mode développeur sur l'application SmartThings de votre smartphone.

1. Démarrez l'application SmartThings.
2. Allez sur **Tableau de bord** > **Paramètres**.
<img src="/assets/image/configuration/samsung-smartthings/developer_mode_1.jpg" alt="SmartThings developer mode 1" class="img-responsive" width="600" />

3. Appuyez 5 secondes sur **A propos de SmartThings**.
<img src="/assets/image/configuration/samsung-smartthings/developer_mode_2.png" alt="SmartThings developer mode 1" class="img-responsive" width="600" />

4. Activez le mode développeur.
5. Redémarrez l'application SmartThings.

### Lier avec l'application Gladys

1. Appuyez sur **Ajouter un appareil** depuis le **Tableau de bord** de l'application SmartThings.
<img src="/assets/image/configuration/samsung-smartthings/add_testing_device_1.jpg" alt="SmartThings add device 1" class="img-responsive" width="600" />

2. Go to **ADD DEVICE MANUALLY** and click **My Testing Devices**. You can now see and add your self-published devices.
<img src="/assets/image/configuration/samsung-smartthings/add_testing_device_2.jpg" alt="SmartThings add device 2" class="img-responsive" width="600" />

3. Confirm the connection by selecting **ALLOW** on Gladys web page.
