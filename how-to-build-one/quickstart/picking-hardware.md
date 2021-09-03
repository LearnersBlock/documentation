# Picking hardware

We support a number of different hardware platforms, ranging in power and price to suit your needs. They are ordered here starting with the cheapest through to the most expensive:

* [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
* [Orange Pi Zero LTS 512MB](http://www.orangepi.org/orangepizerolts/)
* [Raspberry Pi 4 Model B 2GB](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/)
* [Balena Fin](https://www.balena.io/fin/?)

{% hint style="info" %}
We provide a [Raspberry Pi 2](https://downloads.learnersblock.org) and [Raspberry Pi 3 image](https://downloads.learnersblock.org) for those who already have the hardware. We do not recommend buying a Pi 2 or 3 however, but to instead buy the Pi 4 due to its improved features at around the same cost, which is why the Pi 2 and 3 are not included in this documentation.
{% endhint %}

While there are lots to distinguish between the hardware, here is an overview of what we deem to be particularly noteworthy:

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">Known Issues</th>
      <th style="text-align:left">Power</th>
      <th style="text-align:left">Value</th>
      <th style="text-align:left">Availability</th>
      <th style="text-align:left">Features</th>
      <th style="text-align:left">Durability</th>
      <th style="text-align:left">Wi-Fi</th>
      <th style="text-align:left">Storage</th>
      <th style="text-align:left">Approximate cost (before shipping)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href="https://www.raspberrypi.org/products/raspberry-pi-zero-w/">Raspberry Pi Zero W</a>
      </td>
      <td style="text-align:left">
        <p>Portainer unavailable.</p>
        <p></p>
        <p>Not capable of connecting to 5GHz WiFi networks.</p>
      </td>
      <td style="text-align:left">Dated hardware, which no longer provides much bang for your buck.</td>
      <td
      style="text-align:left">Incredibly low cost, for those really needing to cut costs</td>
        <td style="text-align:left">Good distribution, but limited in the quantities you can order at once</td>
        <td
        style="text-align:left">Provides the bare minimum needed to run the Block</td>
          <td style="text-align:left">Tried and tested, produced by a reliable manufacturer</td>
          <td style="text-align:left">Built in Wi-Fi, but with no aerial impacts the range</td>
          <td style="text-align:left">SD Card</td>
          <td style="text-align:left">$10USD</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="http://www.orangepi.org/orangepizerolts/">Orange Pi Zero LTS 512MB/1GB</a>
      </td>
      <td style="text-align:left">Issues with the Wi-Fi chip and firmware can occasionally prevent connecting,
        particularly on older releases of the device.</td>
      <td style="text-align:left">Its Quad-Core processer makes this a significant improvement over the
        Raspberry Pi Zero W. The 1GB model for a little more money will provide
        the ablity to run more applications from the App Store.</td>
      <td style="text-align:left">Excellent value for money, although more per unit than the Raspberry Pi
        Zero</td>
      <td style="text-align:left">Shipping from China means this may take longer to arrive. But it will
        post to a wide range of countries making the availability good.</td>
      <td
      style="text-align:left">An Ethernet Port and USB Port make this feature rich hardware expanding
        the possibilities for your Learner&apos;s Block</td>
        <td style="text-align:left">Runs a little hotter than other units, that may result in slowdowns if
          in extreme heats and direct sunlight.</td>
        <td style="text-align:left">An included aerial gives the range a healthy boost</td>
        <td style="text-align:left">SD Card</td>
        <td style="text-align:left">$17USD+</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://www.raspberrypi.org/products/raspberry-pi-4-model-b/">Raspberry Pi 4 Model B 2GB</a>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">A powerful system which is a significant step up from the others. Provides
        a good basis for running multipule applications from the App Store.</td>
      <td
      style="text-align:left">A step up from the Orange Pi Zero LTS may feel worth the splurge, but
        will begin to add up if buying a large number of units</td>
        <td style="text-align:left">Good distribution, but limited in the quantities you can order at once</td>
        <td
        style="text-align:left">Quad-Core processor, 2GB of RAM (no need to go higher) and a Gigabit Ethernet
          port means this hardware could be plugged into a school network to handle
          larger numbers. it does mean a larger form factor that won&apos;t fit in
          your pocket like the others.</td>
          <td style="text-align:left">Tried and tested, produced by a reliable manufacturer</td>
          <td style="text-align:left">No aerial, but the newer hardware and technologies provide a good range.
            Ethernet connectivity will allow for more users, but Wi-Fi is unlikely
            to support more users than the Orange Pi Zero LTS 512MB.</td>
          <td style="text-align:left">SD Card</td>
          <td style="text-align:left">$30USD</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://www.balena.io/fin/?">Balena Fin</a>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">An industrial powerhouse, designed for professional use in high-end manufacturer.
        Very few will benefit from this sort of power.</td>
      <td style="text-align:left">Unlikely that the majority of users will need what this offers.</td>
      <td
      style="text-align:left">Supports large orders, but distribution overseas more limited that the
        others as units will often come from the US.</td>
        <td style="text-align:left">Ethernet and USB Ports</td>
        <td style="text-align:left">Among the best in class</td>
        <td style="text-align:left">Designed for Internet of Things devices, Wi-Fi connectivity is central
          to its design</td>
        <td style="text-align:left">Built in 8/16/32/64 GB options.</td>
        <td style="text-align:left">$200USD+ (will require additional hardware on top of this cost)</td>
    </tr>
  </tbody>
</table>

You can find places to buy each by clicking on the links above which will take you to the manufacturer's website.

{% hint style="info" %}
A little indecisive? Our personal choice is the Orange Pi Zero LTS 512MB, for its well-rounded features and power for a relatively low cost.
{% endhint %}

{% hint style="warning" %}
While 512mb of memory is sufficient to run the Learner's Block platform, if you are planning to run several applications or demanding applications it would be better to opt for devices with 1gb of more. 
{% endhint %}

