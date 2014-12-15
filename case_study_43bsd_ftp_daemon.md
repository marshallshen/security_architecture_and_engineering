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



