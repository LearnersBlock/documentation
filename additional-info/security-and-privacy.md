# Security & Privacy

Learner's Blocks are designed to be used offline or on private Wi-Fi networks, which reduces security risks significantly. Yet we still build towards making them secure enough to be used in other more public environments just to be sure. 

{% hint style="info" %}
We do not have access to your Block or any way to gain access to your Block, even when they are online. Nor can we identify who owns each Block, or what content is being stored on it. While this does make offering support more difficult, we decided to put security and privacy first and foremost. 
{% endhint %}

### Updates

Security begins with the ability to send timely updates to your Block. A mechanism for regular, reliable, and verifiable updates, gives you the tools you need to keep your Block up to date and protected against attacks.

Our Blocks are focused on the principle of least privilege — permissions are given only as necessary, and no information is available to any account or Block unless it is required for the tasks being performed. 

The core mechanism for implementing this security approach is through API access control. By controlling access to the API, the actions that are permitted, and the available communication channels, we can protect fleets at all points of entry.

In this document, we will further explain how the infrastructure implements access control across the entire lifecycle, from Block access and runtime management, to the image build process, and finally to the API and backend services.

### Block access

Block access is managed by [balenaOS](https://www.balena.io/docs/reference/OS/overview/2.x). BalenaOS is a thin Linux environment that supports the services and user application containers. It is built using [Yocto Linux](https://www.yoctoproject.org/), the de facto standard for building lightweight embedded Linux environments. Using Yocto allows us to build images that contain no unused or unnecessary code in either userspace or the running kernel, minimising the Block's available attack surface. All software running on Blocks is 100% open source and can be independently audited and verified.

When an image is downloaded and flashed to a Block, it comes with a provisioning key that allows Blocks to be added to a specific application. When the Block boots up for the first time, it uses the provisioning API to register itself with our server. A new Block entry on the backend is created, and a Block API key for this Block is generated. Once the provisioning is successful, the provisioning API key is deleted from the Block. 

If a Block is compromised, the Block API key can only be used to read information about the Block or the application the Block is associated with, not the content on it. A key can be removed and revoked if a Block is compromised by simply deleting the Block from our server.

A Block API key also allows a Block to request an application update. When a Block requests an update, this API key is sent and authenticated with our server. Once the API key has been authenticated, a Docker pull is initiated on the Block.

Both the Docker pull request and the actual image download process are performed using HTTPS, so are TLS encrypted. HTTPS connections are always outbound from the Block to the service, meaning that no inbound connections are created and no inbound ports on the firewall are required.

Locally, users can connect to the Block using the built in Wi-Fi network and visit the application through their web browser. We opted to use an open Wi-Fi network for ease of use and HTTP over HTTPs connections to allow for offline compatibility. While these practices are not recommended for connecting over the internet, using locally the risks involved are outweighed by the performance gains and ease of user experience. 

On the Block itself, SSH and other services for connecting and controlling the Block are disabled. The settings interface can be protected by a password set in your control panel. Authentication between the settings panel and backend service of the Block is secured using JWT tokens. 

When you set a password on your Block through the settings panel, your password is hashed using BCrypt SHA256 encryption before being stored in the local database. We have no access to this database. If you lose your Block or it is stolen, the password you set cannot be easily read by an attacker, however, as is always good password practice, we recommend you do not use the same password on the Block as you use in other places as a concerted effort to brute force weak passwords may be successful.

### Runtime management

#### VPN

Balena uses [OpenVPN](https://openvpn.net/) to control the Block state \(e.g. Block reboot, Block shutdown, application restart, etc.\). Blocks only connect outbound to the VPN and all traffic over the VPN is encrypted with TLS.

The Balena VPN disallows Block-to-Block traffic and prohibits outbound traffic to the Internet. If a Block were compromised, this ensures that it cannot contaminate another Block.

By default, the VPN is disabled on the Block. When the VPN is enabled, SSH access is available but we do not include SSH keys on your Block, subsequently denying access to the Blocks through the VPN. 

#### Ports used

All communication between Blocks and the service are outbound from the Block. Ports that are used by Blocks are:

| Port | Protocol | Status | Description |
| :--- | :--- | :--- | :--- |
| 53 | UDP | Required | DNS: used by Blocks to resolve hostnames for connection to the service |
| 123 | UDP | Required | NTP: used by Blocks to synchronize time |
| 443 | TCP | Required | HTTPS: used by Blocks to poll for updates and to download application and host OS updates.  OpenVPN: used by Blocks to connect to provide real-status, control, and an interactive terminal \(optional service\) |

#### Block metadata

Blocks contain metadata that identifies the Block, application, and state of deployed software. This metadata is used to track the state of the Block within our servers and to associate the Block with a specific application.

Currently, metadata such as Block identifiers or WiFi credentials are not encrypted on disk by default. This is because most commercially available Blocks do not support any form of hardware-level encryption, meaning that the decryption keys for this data would have to be stored in an accessible area of the Block. Storing the keys with the encrypted data means that it is trivial for anyone with physical access to the Block to decrypt the data at any point, rendering the encryption itself moot. We however, do not have any access to your Block, and therefore pose no risk of leaking keys externally. 

### Building images

The first step in deploying an application to the Blocks is to build a Docker image that contains everything necessary to run the application.

Balena maintains a repository of base images which are at the foundation of the Learner's Block application. These base images are built by the Balena build infrastructure, so they inherit all the security protections provided to application images. 

Any resource added to base images is verified by GNU Privacy Guard \(GPG\) signatures where available, or a SHA256 checksum based on the original source material \(if a GPG key is unavailable\) to ensure that all included files are verified.

For example, some base images include the Python language runtime. Balena downloads the Python source for building and verifies checksums and signatures to be sure the Python website was not compromised or that no man-in-the-middle attacks have occurred.

Once user application container images are built, they are pushed to the Docker registry. Only the builder has permission to write to the Docker registry, preventing tampering with the images from external sources.

### The API and backend

The API provides a central mechanism for authentication, requesting information, and making changes to the database. The API manages communication both internally among the backend services and externally for users and Blocks.

The API interface is based on the Open Data \(OData\) format. All requests are authenticated with an API token.

When possible, all backend services and components are run with user-level permissions. Where permission escalation is required, it is performed temporarily and de-escalated as soon as the escalated process is complete. This reduces the risk of a particular backend component being leveraged to compromise other components or other users' data and processes.

HTTPS is mandatory for all services internally, meaning no data is transmitted unencrypted between servers.

Our backend service is hosted on [Hetzner](http://hetzner.com) and on its own server, isolated from any other service. 

