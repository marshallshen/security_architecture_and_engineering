# The Internet of Things
## What is the "Internet of Things"?

- Non-computing device with CPU and connectivity.
- Thermostats, fitness sensors, smart TVs.

### Embedded Systems:

- Specialized CPUs.
- Dedicated CPU for particular purpose
- Embedded system is used: cheaper to add a CPU and one-time programming than adding random logic.

### Security of embedded systems

- Embedded systems run programs, programs can be and will be buggy.
- Does the attacker have enough `access` and `knowledge` to launch an attack?
> My coffee maker has CPU, can attacker launch any worthwhile attack to my coffee maker?
- What is threat model?

> Attack against smart tvs - send malicious TV programs to your TV - now that's a valuable attack! Captain midnight attack (TODO)

> Attack against `tire pressure sensor`: tire pressure sensor being put in the car by manufacterers. UC San Deigo researchers built a transmitter to confuse pressure sensor to notify drivers that the tire pressure is low.

### Attacks against embedded systems

* Passwords: people do not change password on many devices.
* Ordinary hacking: 
> SQL injections; (Tesla has embedded Web Browsers). Modern cars have 60-70 CPUs, and they are all inter-connected.
* Data-driven attacks: [malicious `mp3` file](http://www.howtogeek.com/127154/how-hackers-can-disguise-malicious-programs-with-fake-file-extensions/).

> Attacks against embedded systems are `harder` to handle: people have less knowledge on password; people don't know about installing patches of embedded system (it's worse than computer attack in many ways). 

> Worse, manufacturers stopped supporting the gadgets.

> Famous holes in internet of things: HP printers; [baby monitor cameras](http://www.consumeraffairs.com/news/hacker-hijacks-baby-monitor-to-scream-at-infant-in-the-middle-of-the-night-042814.html).

## loT Architecture

* Things talk to `Hubs`.
* `Hubs` talk to `Vendor Sever`.
* `Manger` talk to `Things` via `Hubs`.
* Things don't always have right interface with Internet.

### Home loT

* Local managers (maybe a phone app) talk to hubs.
* Hubs talk to devices via private protocols.
* Hubs talk to vendor servers.
* Things may talk to each other via hubs, but probably use the `vendor servers`.
* `Vendor servers` may talk to each other.

### Vendor Servers
* Many devices cannot be called directly (e.g. Nest thermostats).
* Devices may not have CPU power for some tasks (e.g., voice recognition on Amazon Echo, speech recoginition is costly task, Echo sends data to server).
* Vendors like to gather data.

### Privacy and loT
> Please be aware that if your spoken words include personal or other sensitive information, that information will be among the data captured and transmitted to a third party.

* [Smart TV that records personal data](http://www.brennancenter.org/analysis/im-terrified-my-new-tv-why-im-scared-turn-thing)

### Security of loT architecture

Any component can be attacked: `things`, `hubs`, `servers`, `links`.

> How to hack each component? Who can hack (component)? What are the consequences (of component being hacked)?

#### Link Security
* E.g. home WiFi networks
* Easy to encrypt links
* Primary source of a compromised link: devices at either end of I/O, say, a corrupted firmware.

#### Ownership
* E.g. who can control my Nest thermostat?
* E.g. if I sell my house to other people, should I still have control over the Nest thermostat of that house?
* Many smart devices have little or no user interface.






