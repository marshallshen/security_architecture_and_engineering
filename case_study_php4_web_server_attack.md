# Case study: PHP4 web server attack

### What patterns to look for
* Bad requests (with authentication failure).
* Anything mentioning `/etc/`, where many sensitive information is stored.
* Attempts to execute commands for functions other than emails and netnews.