# System calls for analysis

## `mount` command
> Attach some device as a subtree at some point in the file system

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

Why `setuid`: allow normal user to have priviledge operations

## `strace` system Call Tracing:
> `strace` runs the specified command until it exits. It intercepts and records the system calls which are called by a process and the signals which are received by a process. The name of each system call, its arguments and its return value are printed on standard error or to the file specified with the -o option.

## `ltrace` trace library calls:
> `ltrace` is a program that simply runs the specified command until it exits. It intercepts and records the dynamic library calls which are called by the executed process and the signals which are received by that process. It can also intercept and print the system calls executed by the program.

## `strings` coomand
Looks at a file, and print out anything that looks like a character string.

```bash
$ strings mount | more
```