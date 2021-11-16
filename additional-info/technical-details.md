# Technical details

We have intentionally tried to keep the documentation as lean as possible in order to avoid overwhelming users with the technical details. Now we have a little space, let’s get into some more specifics around what the Block does, and how.&#x20;

## Operating System

At the base of our project is [Balena](https://www.balena.io), an open-source project and set of tools for building, deploying and managing fleets of Blocks. Each Block runs BalenaOS, based on Yocto Linux but heavily customised for reliability and low resource Blocks. It is a read-only OS to avoid risks of corrupting data on SD memory cards and to minimise writes to the Block. Within the OS is a bespoke variation of Docker to run required services in isolated containers. The result is an extremely stable and durable operating platform (so stable in fact, it is even [used in space!](https://www.balena.io/blog/beyond-the-cloud-docker-containers-in-space/)).&#x20;

## Updates

Each Block is connected to the [Balena Cloud](https://www.balena.io/cloud) infrastructure. This service allows security, stability, language and feature updates to be deployed to Blocks when they come online.&#x20;

Updates are installed automatically and in the background. Individual layers of each container are updated rather than the entire container in order to reduce data usage. Only after installations complete successfully are previous versions removed in order to ensure maximum uptime and to reduce risks of Blocks being corrupted if disconnected during updates.&#x20;

Updates are triggered at key intervals such as when the Block loads. This ensures the data usage required during everyday operation of the Block is as low as possible. &#x20;

This service is not required by your Blocks to operate, you can run entirely offline by not connecting to a nearby internet enabled WI-FI Network. &#x20;

## Learner's Block Web Server

One of the core functions of the Learner’s Block is the ability to host your own website. Running on each Block is NGINX and PHP8-FPM ready to serve your files as soon as you drop them in the ‘website’ folder through the [File Manager](../how-to-use-it/adding-resources.md) accessed in your browser.&#x20;

For more advanced hosting options, you can benefit from [Portainer](../how-to-use-it/advanced-features/using-portainer.md).

## Learner's Block Resource Consumption

Each Block type will use slightly different amounts of resources, although all hover around 2-3GB of storage and 250MB of RAM in order to run the base Learner’s Block platform. SWAP memory is disable in order to reduce memory card wear.&#x20;
