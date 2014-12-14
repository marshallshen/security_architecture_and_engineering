# After An Attack
### Sometimes bad guys win
> What to do if a machine is compromised?

> How to assess the damage?

> How to recover?

E.g. 2014 Sony Pictures were hacked by North Korea as the government isn't pleased with one screened pictures. 
TODO: Find news link

## How is a machine compromised?
* 0-day attacks? Attacks that are never seen before.
* Carelessness? (biggest case) Hackers with specialized knowledge creates phishing emails to obtain information.
> Spear phishing (TODO): hacker fakes information based on your background, making the fake information sound more convincing.
* Insider attacks? It's very hard to prevent (Snowden case). Combine insider attack with phishing emails, someone inside sends tailored fake information to obtain access from you, is even worse.
> Insider case study:
1990s, one guy wants to still passwords from top executives. He sets up phone modem, and try to reroute phone modem from company to local phone modem.. Eventually he got caught.

## Damage Assessment
* What has to be thrown out?
* What can be saved?
* How did the bad guys get in?
Generally, it's not possible to cleanse compromised system. Usually `reformat your disk and reinstall`. Today even that's not enough, NSA has demonstrated that it can hack into MacBook batteries (modern PC batteries have CPUs).

## Why attacks happen?
* Previously, hackers attack systems to show off.
> Shut down networks, cause it's fun!
* Gradually, hackers attack systems for money (hacking for profit).
> Don't shut down networks cause it's not going to make money. Steal valuable information. Hackers got paid to launch attacks.
* Recently, state governments and organizations launch large scale attacks (Ex. China-US cycber war; Target, Home Depot credit card system compromise).

## Hidden Back Doors
* Cron jobs
* Programs buried in someone's .profile
* Modern systems have `many ways` to launch programs at boot time.
* Trojan horses in commands likely to be executed by `root`.
* Many more!

### Self-repairing Malware
* Malware contains two or more programs with back door.
* Each malware check the other malware's presence.. If not exist, download the other one.

### Bots and Boats
* Many infections these days turn machines into "bots".
* Modern bot software can upgrade itself.
* Bots can download different payloads -- spam engines, DDos engines, keystroke loggers, etc.

> After attack of compromised machine..
* The attacker has access to all network-accessible resources of compromised machine.
* Home Depot incident: attackers got into home depot main server, then they found out what are the servers for home depot point-of-sale system.
* Attacker can launch a second attack after first attack succeeds: send phishing emails to internal staff to gain more information.

### Backups are your friend
* Back up your system frequently.
* Make sure you have a 0-day backup, from before the system went live.
* Recover your data, `not the program`, from backup.
* If you have good backups, you could restore to another machine and compare files $$\rightarrow$$ very time-consuming.

### Tripwire
* Create a cryptographic checksum of each file.
* To detect changes, the program re-calculate the checksum.
* Easier said than done.








