# Embedded Systems (Smart Devices)

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
* Data-driven attacks: [malicious mp3 file](http://www.howtogeek.com/127154/how-hackers-can-disguise-malicious-programs-with-fake-file-extensions/).

> Attacks against embedded systems are `harder` to handle: people have less knowledge on password; people don't know about installing patches of embedded system (it's worse than computer attack in many ways). 

> Worse, manufacturers stopped supporting the gadgets.

> Famous holes in internet of things: HP printers; [baby monitor cameras](http://www.consumeraffairs.com/news/hacker-hijacks-baby-monitor-to-scream-at-infant-in-the-middle-of-the-night-042814.html).
