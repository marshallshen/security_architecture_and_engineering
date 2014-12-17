## chroot
- Make a process believe that some subtree is the entire file system $$\rightarrow$$ file outside of this subtree simply don't exist.
- Set up a subdirectory to be the file system of the entire file tree.
- Prevent `cd ../` attack.

### Challenge
- Need `entire` file system set up within the subtree.
- Still vulnerable to root compromise
    * Suppose an ordinary user could use `chroot()`
    * Create a link to `su` command
    * Create `/etc` and `/etc/passwd` with a known root password
    * When `sudo su` within sub directory, can escape from `chroot()`.
- Doesn't protect network identity

#### Setup chroot
```
# mkdir /usr/sandbox /usr/sandbox/bin
# cp /bin/sh /usr/sandbox/bin/sh
# chroot /usr/sandbox /bin/sh
chroot: /bin/sh: Exec format error
# mkdir /usr/sandbox/libexec
# cp /libexec/ld.elf_so /usr/sandbox/libexec
# chroot /usr/sandbox /bin/sh
Shared object "libc.so.12" not found
# mkdir /usr/sandbox/lib
# cp /lib/libc.so.12 /usr/sandbox/lib
# chroot /usr/sandbox /bin/sh
Shared object "libedit.so.2" not found
# cp /lib/libedit.so.2 /usr/sandbox/lib
# chroot /usr/sandbox /bin/sh
Shared object "libtermcap.so.0" not found
# cp /lib/libtermcap.so.0 /usr/sandbox/lib
# chroot /usr/sandbox /bin/sh
# ls
ls: not found
# echo sandbox >/Escape
# ˆD
# ls -l /usr/sandbox
total 4
drwxr-xr-x 2 root wheel 512 Nov 1 21:50 bin
-rw-r--r-- 1 root wheel 7 Nov 1 22:31 Escape
drwxr-xr-x 2 root wheel 512 Nov 1 22:31 lib
drwxr-xr-x 2 root wheel 512 Nov 1 22:30 libexec
```
