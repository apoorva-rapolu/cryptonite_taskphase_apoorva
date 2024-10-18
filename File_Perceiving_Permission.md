## Changing File Ownership
`chown` can only be invoked by the root user. It is used to change the owner of a particular file to the a particular user. <br>
 The challenge wants us to change the owner of the `/flag` file to the `hacker` user
```
hacker@permissions~changing-file-ownership:~$ chown hacker /flag 
lrwxrwxrwx 1 hacker hacker    5 Oct  8 17:52 not-the-flag -> /flag 
pwn.college{goPGpMxGIolqcOPwbUYW_WkOnhA.dFTM2QDLxgDO0czW}
```

## Groups and Files
Group ownership can be changed with the `chgrp` (change group) command. <br>
Here, we are changing the group ownership of  `/flag` file to `hacker`
```
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{4AxdBwiTRWthLpSRrbFhDfDGuxq.dFzNyUDLxgDO0czW}
```

## Fun with group names
Using `id` command to check the name of the group.
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp22053) groups=1000(grp22053)
```
The name is `grp22053` <br>
Changing the group ownership using `chgrp` command and then catting the file to obtain the flag.
```
hacker@permissions~fun-with-groups-names:~$ chgrp grp22053 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{8CqbZuAZI5qsqwh52Y0Wvv7mBvT.dJzNyUDLxgDO0czW}
```

## Changing Permissions
```
hacker@permissions~changing-permissions:~$ chmod u+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
cat: /flag: Permission denied
```
changing the permissions with `chmod u+r /flag` did not allow me to <br>
read the `/flag` file, which is likely due to the file being owned by the `root` user. <br>
So I changed the permissions of the `/flag` file to allow read access to everyone by using `a+r`. 
```
hacker@permissions~changing-permissions:~$ chmod a+r /flag
```
and then used `ls -l` to check the permissions:
```
hacker@permissions~changing-permissions:~$ ls -l /flag
-r--r--r-- 1 root root 58 Oct 18 15:00 /flag
```
now that everyone can read the file, I used `cat` command to access the file and obtain the flag.
```
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{M5Zyy2ej_pn8edd9G8OG06-lvxc.dNzNyUDLxgDO0czW}
```

## Executable Files
`a+x`: This adds execute permission for all users (owner, group, and others) (CHATGPTed this to know about the command)
```
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r-xr-xr-x 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{YqHZfIh-0kv4NUdLALXqbHDiLge.dJTM2QDLxgDO0czW}
```

## Permission Tweaking Practice
Phew!! This was long <br>
using `u` for user, `g` for group and `o` for others <br>
and `+` to add and `-` to remove <br>
`r`(read) , `w`(write) and `x` (execute)
### Round 0 (of 8)!
```
Current permissions of "/challenge/pwn": rw-r--r--
Needed permissions of "/challenge/pwn": -w-------
hacker@permissions~permission-tweaking-practice:~$ chmod u-r,go-r /challenge/pwn
You set the correct permissions!
```
### Round 1 (of 8)!
```
Current permissions of "/challenge/pwn": -w-------
Needed permissions of "/challenge/pwn": -w-r--r--
hacker@permissions~permission-tweaking-practice:~$ chmod go+r /challenge/pwn
You set the correct permissions!
```
### Round 2 (of 8)!
```
Current permissions of "/challenge/pwn": -w-r--r--
Needed permissions of "/challenge/pwn": ---r--r--
hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
You set the correct permissions!
```
### Round 3 (of 8)! 
```
Current permissions of "/challenge/pwn": ---r--r--
Needed permissions of "/challenge/pwn": ---------
hacker@permissions~permission-tweaking-practice:~$ chmod go-r /challenge/pwn
You set the correct permissions!
```
### Round 4 (of 8)!
```
Current permissions of "/challenge/pwn": ---------
Needed permissions of "/challenge/pwn": ------r--
hacker@permissions~permission-tweaking-practice:~$ chmod o+r /challenge/pwn
You set the correct permissions!
```
### Round 5 (of 8)!
```
Current permissions of "/challenge/pwn": ------r--
Needed permissions of "/challenge/pwn": ---------
hacker@permissions~permission-tweaking-practice:~$ chmod o-r /challenge/pwn
You set the correct permissions!
```
### Round 6 (of 8)!
```
Current permissions of "/challenge/pwn": ---------
Needed permissions of "/challenge/pwn": ------r-x
hacker@permissions~permission-tweaking-practice:~$ chmod o+rx /challenge/pwn
You set the correct permissions!
```
### Round 7 (of 8)!
```
Current permissions of "/challenge/pwn": ------r-x
Needed permissions of "/challenge/pwn": r-x---r-x
hacker@permissions~permission-tweaking-practice:~$ chmod u+rx /challenge/pwn
You set the correct permissions!
```
```
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!
```
```
Current permissions of "/flag": ---------
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{E5DUEwI6fITOVCNg1vkMTLB6rLr.dBTM2QDLxgDO0czW}
```

## Permission Setting Practice
This was same as the before one but instead used a new command `=` <br>
`=` is a combination of `+` and `-`. <br>
for example <br>
`chmod u=rw,g=r /challenge/pwn` will set the user permissions to read and write, and the group permissions to read-only <br>
`chmod a=r,u=rw /challenge/pwn` will set the user permissions to read and write, and the group and world permissions to read-only <br>
using `=` and after completing all 8 rounds and then catting `/flag` file to obtain the flag 
```
hacker@permissions~permissions-setting-practice:~$ chmod u+r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{wtUehvmF39xUes_jOBt8lLJt_hr.dNTM5QDLxgDO0czW}
```

## The SUID Bit












