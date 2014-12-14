# System calls for analysis

## `mount` command
> Attach some device as a subtree at some point in the file system. `home/` is a system directory that was `mount` by system call.

```bash
root@mshen: ls /mnt
root@mshen: mount /dev/sdb1 /mnt
root@mshen: ls /mnt
root@mshen: BROTHER text.pdf
```

### Looking on Linux..
```
ls -l /bin/mount
-rwsr-xr-x 1 root root...
```

Why `setuid`: allow normal user to have priviledge operations!

### Trying Mount
```
/bin/mount -t iso9660 /dev/cdrom /mnt/cdrom
mount: only root can do that
$ cp /bin/mount .
$ ./mount -t iso9660 /dev/cdrom /mnt
mount: must be superuser to use mount
```
`Same problem, different message`! The code path is different somehow.. $$\rightarrow$$ How do we find out what's happening?

## `strace` trace system calls:
> `strace` runs the specified command until it exits. It intercepts and records the system calls which are called by a process and the signals which are received by a process. The name of each system call, its arguments and its return value are printed on standard error or to the file specified with the -o option.

### Run `strace`:
```
getuid32() = 7994
geteuid32() = 7994
lstat64("/etc/mtab", st_mode=S_IFREG|0644, st_size=1634, ...) = 0
stat64("/sbin/mount.iso9660", 0xbfffa9a0) = -1 ENOENT (No such file or directory)
rt_sigprocmask(SIG_BLOCK, ˜[TRAP SEGV RTMIN], NULL, 8) = 0
mount("/dev/cdrom", "/mnt/cdrom", "iso9660",
MS_POSIXACL|MS_ACTIVE|MS_NOUSER|0xec0000, 0) = -1 EPERM
rt_sigprocmask(SIG_UNBLOCK, ˜[TRAP SEGV RTMIN], NULL, 8) = 0
...
write(2, "mount: must be superuser to use ..."
```
The message is the *unpriviledged* version.

## `ltrace` trace `library calls`: 
> `ltrace` is a program that simply runs the specified command until it exits. It intercepts and records the dynamic library calls which are called by the executed process and the signals which are received by that process. It can also intercept and print the system calls executed by the program.

```
__strdup(0xbff2abb3, 4095, 0xb7d0a000, 373, 0)= 0x9c3cd28
__strdup(0xbff2aba0, 4095, 0xb7d0a000, 373, 0)= 0x9c3cd38
sprintf("/sbin/mount.iso9660", "/sbin/mount.%s", "iso9660") = 19
```
Can we exploit `springf` by bufferoverflow?

## `strings` coomand
Looks at a file, and print out anything that looks like a character string.

```bash
$ strings mount | more
```