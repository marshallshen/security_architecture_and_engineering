# Log Incidents

# Incidents resolved by logs

### Wikileaks
> What caused Wikileaks?
Weak servers, weak logging, weak physical security, weak
counterintelligence, inattentive signal analysis . . . a perfect storm.

* Manning brought in CDs, but nobody objected..
* No one checked the logs for how much he was downloading..
* Possibly bad personnel security - has Manning been questioned with
  identity clearance?

### Snowden Files

* The public doesn't know what he took, nor how much.
* NSA doesn't know either, possibly due to `inadequate logging`?

### Incident 1: [Shadow
Hawk](http://phrack.org/issues/16/11.html#article)
* An attacker in name of "Shadow Hawk", FBI tracked him down via log files.
* Used `uucp`: dial-up file transfer from `Unix`.
* `uucp` logged all file transfer requests.

### Incident 2: Stalking the Wily Hacker
An astronomer-turned-sleuth traces a German trespasser on our military
networks, who slipped through operating system security holes and
browsed through sensitive databases. Was it espionage?

* Original goal of project: charge authorized users for computer usage
* The book didn't balance, `Cliff Stoll` determined to find out why via log files: some un-authorized user dived into computer center.

### Lesson: good log file facilitates good protection.
* Log files are "extraneous": you don't need them when things are going well.
* Run cron jobs in log file to detect malicious acts.
