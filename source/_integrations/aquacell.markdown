---
title: AquaCell
description: Instructions on how to integrate AquaCell with Home Assistant.
ha_category:
  - Sensor
ha_release: 2024.7
ha_iot_class: Cloud Polling
ha_config_flow: true
ha_codeowners:
  - '@Jordi1990'
ha_domain: aquacell
ha_platforms:
  - sensor
ha_integration_type: device
---

AquaCell is a water-softening device. The [AquaCell](https://www.aquacell-waterontharder.nl/) {% term integration %} allows you to monitor your AquaCell device in Home Assistant.
You will need your Aquacell account information as used in the **AquaCell** app.

This integration also supports [Harvey](https://www.harveywatersofteners.co.uk/) softeners.

## Supported devices

This integration only works softener models which have an <b>i-Lid</b> and are configured through the 'Mijn AquaCell' or 'My Harvey' mobile app.
These models are also recognizable by the required curved salt blocks.
- [AquaCell](https://www.aquacell-waterontharder.nl/aquacell)
- [HarveyArc Water Softener](https://www.harveywatersofteners.co.uk/products/water-softeners/harveyarc-water-softener)

{% include integrations/config_flow.md %}

{% configuration_basic %}
Email address:
  description: The email address used to login to the mobile app used to monitor the softener.
  required: true
  type: string
Password:
  description: The password used to login to the mobile app used to monitor the softener.
  required: true
  type: string
{% endconfiguration_basic %}

## Sensors

This integration provides {% term sensors %} for the following information from the AquaCell device:

- Percentage of salt remaining.
- Time remaining until 0% salt level is reached.
- i-Lid battery level.
- Wi-Fi signal strength.

## Examples

### Send a notification when your salt level is low
You can create an automation that sends a notification when the salt level is low, similar to the official app but more flexible.

### Monitor salt usage over time
You can easily plot the history of the salt level sensors over time, which can give you more insight on usage.

## Data updates
The device does not update frequently, the integration is {% term polling %} new data every day from the cloud.

## Known limitations
- No local API.

## Troubleshooting

### Can’t setup the device
Make sure the device is fully setup through the official app.

## Remove integration

This integration follows standard integration removal, no extra steps are required.

{% include integrations/remove_device_service.md %}
