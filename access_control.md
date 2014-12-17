# Access Control

## Permissin Checking Alorightm
```
if curr_user.uid == file.uid
    check_owner_permissions();
else if curr_user.gid == file.gid
    check_group_permissions();
else
    check_other_permissions();
fi
```

## Owner Permissions
```
$ id
uid=54047(smb) gid=54047(smb) groups=0(wheel),3(sys),54047(smb)
$ ls -l not me
----r--r-- 1 smb wheel 29 Sep 12 01:35 not me
$ cat not me
cat: not me: Permission denied
```