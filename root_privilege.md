# Root privilege

> For various complex reasons, `rsh`, `rlogin`, and `rcp` need to set network connections as root. 

> `They’re horribly insecure for network reasons`.

## How to use `root` privilege?
* We only need root privileges to set up the connection.
* Use an external program for `using root to set up connection`.
    * Method 1: pass an open file descriptor back.
    * Method 2: Fork and pay the price of extra data copies.