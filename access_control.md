# Access Control

### Access Control List
* 9-bit model not always flexible enough
* Many systems (Multics, Windows XP and later, Solaris,
some Linux) have more general Access Control Lists
* ACLs are explicit lists of permissions for different parties
* Wildcards are often used

#### Sample ACL
```
smb.* rwx
4187-ta.* rwx
*.faculty rx
*.* x
```

### Permissin Checking Alorightm
```
if curr_user.uid == file.uid
    check_owner_permissions();
else if curr_user.gid == file.gid
    check_group_permissions();
else
    check_other_permissions();
fi
```

### Owner Permissions
```
$ id
uid=54047(smb) gid=54047(smb) groups=0(wheel),3(sys),54047(smb)
$ ls -l not me
----r--r-- 1 smb wheel 29 Sep 12 01:35 not me
$ cat not me
cat: not me: Permission denied
```

### Directory Permissions
```
$ ls -ld oddball
dr--r--r-- 2 smb wheel 512 Sep 12 01:36 oddball
$ ls oddball
cannot get at
$ ls -l oddball
ls: cannot_get_at: Permission denied
$ cat oddball/cannot get at
cat: oddball/cannot get at: Permission denied
```

