# Deleted Files

### Finding Deleted Files
* Delete a file doesn't delete the data (it just deletes the pointer to the data and mark that memory block as free block)
* Clever program can recover deleted files.
* How to clean up damaged disk `changes all the time`, it depends on current technology (Hard Disk vs. Flask Disk), and you need to rely on experts to cleanse up with current technology.

### Recover deleted files
* Based on file types: different file types $$\iff$$ different byte distributions.
* Example: C program has many "{" and "}"; log files have timestamps!
* Look for matches between the end of one block and the start of the next.
* Look for syntactically correct statement.

### Are deleted files better for forensics?
* A normal file can be overwritten easily
* A deleted file can't be touched
* Sometimes deleted files are more likely to be intact, which is more useful when analyzing the system.