# Fix FTP

### Better grammar
> `Force login` before any other code can execute

```
ftpsess : user pass cmdseq
user : USER SP username CRLF
pass : PASS SP password CRLF
cmdseq : cmd | cmdseq cmd
cmd : CWD SP pathname CRLF
| ...
```

### Break up FTPD
> Tangled code is messy

* Split `ftpd` into two programs:
    * Login handles: check for anonymous ftp, validating password, handle `setuid()` and `chroot()`
    * Exec: performed under-priviledged, do most of the work.
    * Resulting code base is `smaller`: 125 lines for login handles.

### Split port 80
> ftpd is supposed to be on port 20, but only root can bind low-numbered port $$\rightarrow$$ can we give up root privilege after login?

* `setUID` program that binds an open socket to port 20.
* Create a socket `fork/exec()` invoke the program above.
* When it returns, you have a socket.

## What we learned?
* Divide program into privileged and unpriviledged sessions.
* Strong isolation between sections.
* Remove flags $$\rightarrow$$ simplify logic.




