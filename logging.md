# Logging

### Incident 1: Shadow Hawk
* An attacker in name of "Shadow Hawk", FBI tracked him down via log files.
* Used `uucp`: dial-up file transfer from `Unix`.
* `uucp` logged all file transfer requests.

### Incident 2: Stalking the Wily Hacker

* Original goal: charge authorized users for computer usage
* The book didn't balance, `Cliff Stoll` determined to find out why: some un-authorized user dived into computer center.

> Run cron jobs in log file to detect malicious acts.

### What patterns to look for
* Bad requests (with authentication failure).
* Anything mentioning `/etc/`, where many sensitive information is stored.
* Attempts to execute commands for functions other than emails and netnews.

> Shadowed password file: file hashed password is stored, can be only used in `priviledge file`, only `root` can read it.