# Logging

### Incident 1: Shadow Hawk
* An attacker in name of "Shadow Hawk", FBI tracked him down via log files.
* Used `uucp`: dial-up file transfer from `Unix`.
* `uucp` logged all file transfer requests.

TODO: links

### Incident 2: Stalking the Wily Hacker

* Original goal: charge authorized users for computer usage
* The book didn't balance, `Cliff Stoll` determined to find out why: some un-authorized user dived into computer center.

TODO: links

### Lesson: good log file facilitates good protection.
* Log files are "extraneous": you don't need them when things are going well.
* Run cron jobs in log file to detect malicious acts.


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
* Keep logs as flat files (for small sites)
* If possible, store log files in database, it provides sophisticated queries (give me log lines from 12pm to 13pm with words 'Authentication failed').
* Today hardware is cheap enough for services to store all logs. 

### Log patterns to look for
* Bad requests (with authentication failure).
* Anything mentioning `/etc/`, where many sensitive information is stored.
* Attempts to execute commands for functions other than emails and netnews.




