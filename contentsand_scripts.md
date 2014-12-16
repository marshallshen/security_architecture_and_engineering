# Contents and Scripts

## Content Security
- Root (www) should not own contents of users
- "Are scripts allowed to run?"
- In general, all scripts run with the same permissions.
- Scripts can interfere with each other:
    > All the CGI scripts will run as the same user, so they have potential to conflict with other scripts.

### TLS encryption
1. Used by most e-commerce
2. TLS applies public-key encryption
3. How to store key on a computer?
> Store in computer x--,---,---
> It's owned by root, and reads in at startup before changing UIDs.

### Authentication
1. Two basic types: `passwords` and `client-side certificates`.
2. `Passwords` should never be used without encrypting the network connection.
3. Ultimately, the client's identity is Apache UID.

## Script Security
1. Allow scripts only in certain directories.
2. suEXEC runs to switch users to run.
3. suEXEC has > 20 checks before switch users, for example:
    - suEXEC is only executable by www
    - is the directory NOT writable by anyone else?

#### Safety pratice
1. Do not permit execution of C or C++ programs
2. Use web server access control
3. `Challenge`: if all scripts run with the same permission, and if local users have read-access to user content, how can a user do safe upload?
4. Script access control is difficult


### Phishing:
1. trick people into sending their passwords to the wrong site.
2. People could check the site's certificate
3. Safety pratice
    > Use a password manager such as 1password!