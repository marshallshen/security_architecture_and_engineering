# Tools part 2: Fuzzing and more

### TOCTTOU races
> TOCTTOU: time of check to time of use

`stat()` vs. `fstat()`

`stat()` works on filenames, while `fstat()` works on file descriptors.

The major reason is security: if you first `stat()` the file and then `open()` it, there is a small window of time in between where the file could have been modified (or had its permissions changed, etc) or replaced with a symlink.

### Fuzzing
> Single most powerful and used fuzzing tools; used by testers & attackers.

> Trying different inputs to break system, `systematically`.

* Random: no knowledge of input formats.
* Smart: handles input formats, checksum, etc.
* Black box: smart, but with no validation of code coverage.
* White box: systematically test different code paths.

Read more on [fuzz testing](http://en.wikipedia.org/wiki/Fuzz_testing).

### High level attacks from Tiger Team
* Network attacks: DDos attack.
* Social attacks: social engineering; talk people into giving you what you want.
* Physical attacks: e.g. physically break into the building, say, a bank.
* Infiltration: get a low-level job at targeted company, become insider, launch insider attack.

### Conclusions
* Programs leak a lot of data while executing.
* Run `strace` and `ltrace` are powerful, even if the executable is read-protected.