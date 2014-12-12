# Logging

#### Incident of Shadow Hawk
* An attacker in name of "Shadow Hawk", FBI tracked him down via log files.
* Used `uucp`: dial-up file transfer from `Unix`.
* `uucp` logged all file transfer requests.

### What patterns to look for
* Bad requests (with authentication failure)
* Anything mentioning `/etc/`, where many sensitive information is stored.

> Shadowed password file: file hashed password is stored, can be only used in `priviledge file`, only `root` can read it.