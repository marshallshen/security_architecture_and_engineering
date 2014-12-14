# Analyze a hacked system

### Work with a Copy
* `Never` try to work with a live disk.
* `Make a copy`: preferably an image copy.
* `Don't use anything` that will change file access times.

### Live CDs
If you don't a spare machine, try to boot a `live` CD: a bootable, runnable system.

### Things to look for
* What files were changed recently?
* Look at `ctime`, not just `mtime`: `mtime` can be changed by a standard system call.
* Log files: check for suspicious entries from compromised machines.
    * Outbound connections from known-infected machines can indicate attempts to spread the problem.
    * Inbound connections `to` infected machine can show how the problem started.
* `Funk filename`: 
    * "..." (3 dots)
    * "bin "(trailing blank)
    * "usr/lbb" (instead "user/lib") $$\rightarrow$$ you see what you want to see.





