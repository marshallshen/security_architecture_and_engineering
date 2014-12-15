# 4.3BSD FTP Daemon (1986)

> Implemented File Transfer Proctol (FTP)

> `2600` lines of code

> Ancestor to many of today's FTP daemons

## FTP protocol basic features
* Download and upload files
* Sequence of simple, 3- and 4-letter commands (flagging)
* Commands have zero or one operands
* Responses prefixed by 3-digit result code
* Must support anonymous ftp
    * unauthenticated access to restricted set of resources
* Permit login with username and password

### Sample FTP session
* Status code
    * 331: only one command can allow: PASS
    * 200s: success
    * 100s: intermediate states
    * 400s and 500s: temporary and permanent failure

```
$ ftp ftp.netbsd.org
220 ftp.NetBSD.org FTP server (NetBSD-ftpd 20040809) ready.
USER anonymous
331 Guest login ok, type your name as password.
PASS anything
230 Guest login ok, access restrictions apply.
LIST
150 Opening ASCII mode data connection for ’/bin/ls’.
(data transferred on separate TCP connection)
226 Transfer complete.
FBAR
500 ’FBAR’: command not understood
```

### Inside FTP
* Read one line at a time
* Use `YACC grammar`
* Logged in check is part of the grammar
* Use `chroot()` to contain anonymouse FTP users

#### YACC Grammar
> Pattern matching
```
cmd : USER SP username CRLF
| PASS SP password CRLF
| CWD SP pathname CRLF
| ...
```
> Problem: the concept is good, but the code was buggy.

### FTP Attack
Consider the following command sequence:
```
USER anonymous # set anonlymous login flag, retrieve anonymous entry from /etc/passwd
CWD ˜root
PASS anything
```
The trick: the `legal sequence` is:
```
USER
PASS
session commands
```
`ftpd` grammar treats all commands the same, including `USER` and `PASS`.

A closer look at the Actual YACC Grammar:
```
cmd : USER SP username CRLF
| PASS SP password CRLF
| CWD check_login SP pathname CRLF # pseudo-rule, just a hook for some C code that checks the logged in flag
| ...
```







