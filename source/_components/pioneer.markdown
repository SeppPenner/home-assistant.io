---
layout: page
title: "Pioneer Network Receivers"
description: "Instructions on how to integrate a Pioneer Network Receivers into Home Assistant."
date: 2016-05-07 08:00
sidebar: true
comments: false
sharing: true
footer: true
logo: pioneer.png
ha_category: Media Player
ha_release: 0.19
ha_iot_class: Local Polling
redirect_from:
 - /components/media_player.pioneer/
---

The `pioneer` platform allows you to control Pioneer Network Receivers. Please note, however, that the more recent Pioneer models work with [Onkyo](/components/media_player.onkyo/) platform instead.

To add a Pioneer receiver to your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
media_player:
  - platform: pioneer
    host: 192.168.0.10
```

{% configuration %}
host:
  description: The IP of the Pioneer device, e.g., `192.168.0.10`.
  required: true
  type: string
name:
  description: The name you would like to give to the receiver.
  required: false
  default: Pioneer AVR
  type: string
port:
  description: The port on which the Pioneer device listens, e.g., `23` or `8102`.
  required: false
  default: 23
  type: integer
timeout:
  description: Number of seconds (float) to wait for blocking operations like connect, write and read.
  required: false
  type: float
{% endconfiguration %}

Notes:

- Some Pioneer AVRs use the port 23 default and some are reported to use 8102.
- `timeout` is a socket level option and should only be configured if you know what you are doing.
