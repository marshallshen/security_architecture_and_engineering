# (Web Service) Architecture

> Web service is an operation system:
1. Access Control
2. Manage process
3. Database connection

*Can web server benefit from OS access control?*

*What UIDs does the server run under?*

> Difference between `Effective UID` and `Real UID`

> Normally these are the same, but if a program with a set-uid bit set is run, then while the real UID remains that of the user who ran it, the effective UID is that of the user who owns the file.

## Berkely history of web
- Most Unix system reserve < 1024 for root
- Web servers listen on port 80, so something `HAS TO` be root in order for web server to start running.
- `Shedding priviege`: Apache starts as root, then forks and sheds privileges.
- Apache serving web pages as non-priviledged user "www"

## Challenges of designing web server
- Web server should be up most time
- Error-resiliency is fundamental for designing web server
- Be smart about `restart` and `retry` is crucial for highly reliable systems.
- `Rollback and recovery`: design for system reliability in the very beginning. E.x. to design a phone network, I must make sure that `phone switch` is up running, if one phone cuts out, it eliminates the phone, but `phone switch` is up on running.

## File permissions
- If the user of the process is not root, it can't open protected files.
- Give web server least privilege needed.
- Use OS to protect system against web server.
- Dijstra's Turing award:
    >underestimate a programmer's ability to get stuff right.

## htaccess
From Wikipedia:
> A .htaccess (hypertext access) file is `a directory-level configuration file` supported by several web servers, that allows for decentralized management of web server configuration. They are placed inside the web tree, and are able to override a subset of the server's global configuration for the directory that they are in, and all sub-directories.[1]

> The original purpose of .htaccess—reflected in its name—was to allow per-directory access control, by for example requiring a password to access the content. Nowadays however, the .htaccess files can override many other configuration settings including content type and character set, CGI handlers, etc.

### Security problems by people
- Say sys admin doesn't figure the permissions for files the way user wanted, user configures .htaccess that overrides system access control settings.
- Apache solution: have a configuration that determines who wins the access control (htaccss or system permission)
- System admin can get the permissions wrong!

### Web server security features
- Root (www) should not own contents of users
- "Are scripts allowed to run?"
- In general, all scripts run with the same permissions.
- Scripts can interfere with each other:
    > All the CGI scripts will run as the same user, so they have potential to conflict with other scripts.

### Restricting scripts
1. Allow scripts only in certain directories.
2. suEXEC runs to switch users to run.
3. suEXEC has > 20 checks before switch users, for example:
    - suEXEC is only executable by www
    - is the directory NOT writable by anyone else?
## Safety pratice
1. Do not permit execution of C or C++ programs
2. Use web server access control
3. `Challenge`: if all scripts run with the same permission, and if local users have read-access to user content, how can a user do safe upload?
4. Script access control is difficult

## TLS encryption
1. Used by most e-commerce
2. TLS applies public-key encryption
3. How to store key on a computer?
> Store in computer x--,---,---
> It's owned by root, and reads in at startup before changing UIDs.

## Authentication
1. Two basic types: `passwords` and `client-side certificates`.
2. `Passwords` should never be used without encrypting the network connection.
3. Ultimately, the client's identity is Apache UID.

## Phishing:
1. trick people into sending their passwords to the wrong site.
2. People could check the site's certificate
3. Safety pratice
    > Use a password manager such as 1password!

## Lessons
1. Web servers are `very hard` to secure
2. Tool: OS permissions, application ACLs, script language security, and more.

