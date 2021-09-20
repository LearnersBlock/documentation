---
description: >-
  Portainer allows technical experts to deploy an infinite number of
  possibilities to their Learner's Blocks
---

# Using Portainer

Learner’s Block includes an instance of [Portainer](https://www.portainer.io) - an open-source container management tool - allowing you to deploy micro-services that can run software in its own isolated environment.

{% hint style="warning" %}
Raspberry Pi Zero has a dated ARM architecture that Portainer does not support, and therefore is not an option on that hardware.
{% endhint %}

We included this facility, to allow users to customise and use their Learner's Blocks in whichever way they deem necessary. Thanks to the inclusion of Portainer, you can host complex apps and websites by including backends, Node instances or anything else you can think of to build.

By default, Portainer is not running to avoid use of unnecessary services. You can start and stop it on your Block in the Advanced tab of the Control Panel. A URL to access Portainer will be provided in the Control Panel that accounts for any changes to your Blocks URL and Wi-Fi SSID but will typically be `http://lb.local/portainer/`.

On first use the login details will be:

```text
username: lb
password: lb
```

{% hint style="info" %}
[Docker Hub](https://hub.docker.com) is a comprehensive database of available containers that can be pulled to the Learner's Block via Portainer. While it is not the only database, it is a good place to start finding an array of operating systems and common services.
{% endhint %}

