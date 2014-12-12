# Logging

> ### What is shadowed password file
> File hashed password is stored, can be only used in `priviledge file`, only `root` can read it.

### Location of log files
* Many different system components can produce logs
* Logs can be expensive, and aren't enabled by default.

#### Web logs
* Timestamp, with time zone
* IP address
* `Request can lie`: sophisticated attacker can fake some information, like what machine this request is sending from?

#### Problems of logging
* How to detect problems
* Need log file scanners to pick out `interesting` patterns
* What are some `interesting` patterns?
    * Bad requests (with authentication failure).
    * Anything mentioning `/etc/`, where many sensitive information is stored.
    * Attempts to execute commands for functions other than emails and netnews.
    * Ananomalous patterns: `too many misses` or `too-long URLs`, which can lead to buffer overflow.
* Correlate log files across different component $$\rightarrow$$ making timestamp consistent across components is super important $$\rightarrow$$ `UTC` across.

#### Log correlation
* Across machine of one site
* Across sites
* Watch out for privacy issue: 
    * beaware giving up `user information`!
    * What sites users are reaching (HIV, gun purchase)?

#### Types of logs
* Routing processing
* Error message
* Authentication events
* Request / Reponse

#### Processing logs
* Primary rule: retain raw data as long as possible (Do not delete log data!).
* Be suspicious: log files often contain enemy-supplied data.
* Be `especially careful` if you use a web browser to look at log file data: it may contain JavaScript-based pop-ups.
* Crunch log down to manageable size; pick out interesting items.

#### Storing logs
* Keep logs as flat files (for small sites).
* If possible, store log files in database, it provides sophisticated queries (give me log lines from 12pm to 13pm with words 'Authentication failed').
* Today hardware is cheap enough for services to store all logs. 
* Storing logs at local machine is dangerous: if attacker gets into the machine, logs can be wiped out. 
* `Use a log server`: machine sends log packets to log server, but do not have permission to go into the log server.

#### Log patterns to look for
* Bad requests (with authentication failure).
* Anything mentioning `/etc/`, where many sensitive information is stored.
* Attempts to execute commands for functions other than emails and netnews.

#### Limits of full-traffic logs
* Capturing every packet is hard.
* Solution: set up web proxy (block port 80, 443), store logs in web proxy.

#### Security of log files
* Needs C(confidentiality) I (Integrity) A (Availability).
* Logfiles need to watch out for personal privacy (e.g password).
* `Confidentiality`: Logfiles need to be read-protected.
* `Integrity`: make sure enemy can't tamper with your logs; it is a primary target for many hackers!
* `Availability`: one attack is to fill up log area with innocent garbage, when the log file is full, launch the real attack.

#### Secure logs
* Protocol (with crypto) exists for secure logging.
* Log files are `parts of systems`: the file needs to be consistent and easy to collaborate with other parts of the systems.

> #### How do you know when log file is full?
Research? Yet because disk is cheap nowadays, such attack is hard to launch.





