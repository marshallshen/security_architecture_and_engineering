# Logging
> Lots of systems have very good logs, but few have been examined properly..

### Who can create log files?
* Many different system components can produce logs
* Logs can be expensive, and aren't enabled by default.

### What are some problems of logging?
* How to detect problems
* Need log file scanners to pick out `interesting` patterns
* What are some `interesting` patterns?
    * Bad requests (with authentication failure).
    * Anything mentioning `/etc/`, where many sensitive information is stored.
    * Attempts to execute commands for functions other than emails and netnews.
    * Ananomalous patterns: `too many misses` or `too-long URLs`, which can lead to buffer overflow.
* Correlate log files across different component $$\rightarrow$$ making timestamp consistent across components is super important $$\rightarrow$$ `UTC` across.

### What to log for system security?
* Security events: permission denied, su, use of privileges, authentication failure..
* `Always` log session start/end.
* Be aware trade off between "how complete the log files are" vs. "space and performance (easy to search?) of log file".






