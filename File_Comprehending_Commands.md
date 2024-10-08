## cat: not the pet, but the command!
```
pwn.college{U20TNyCX9dJreFM46HiDVKMcPQh.dFzN1QDLxgDO0czW}
```

cat is used for reading files <br>
cat flag file

## catting absolute paths
```
pwn.college{ASnVa9ULqTIYIz1LZWNY6ZFH6nr.dlTM5QDLxgDO0czW}
```

accessing flag file using cat command `cat /flag`

## more catting practice
```
pwn.college{0Fz44k9hGtdCgs58w0ubX5k4B8O.dBjM5QDLxgDO0czW}
```

flag was hidden in directionary /opt/ida/dbgsrv and it was retrieved by absolute paths using cat command 
 `cat /opt/ida/dbgsrv/flag`

## grepping for a needle in a haystack
```
pwn.college{AVN6dfqPXTplUKdWqe4oLpWFLc6.ddTM4QDLxgDO0czW}
```

using `grep` command to find the text "pwn.college" in the /challenge/data.txt file `grep pwn.college /challenge/data.txt`

## listing files
```
hacker@commands~listing-files:/challenge$ ls 
27185-renamed-run-21425  DESCRIPTION.md 
hacker@commands~listing-files:/challenge$ /challenge/27185-renamed-run-21425 
Yahaha, you found me! Here is your flag: 
pwn.college{owRbeeFw0SyOpuqinOfREDg1TMw.dhjM4QDLxgDO0czW} 
```

## touching files
```
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{0CG15LItv_O-jbnSbTqqyUdTkiF.dBzM4QDLxgDO0czW}
```

## removing files
```
hacker@commands~removing-files:~$ ls
Desktop  delete_me  w
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
Desktop  w
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Ea8s0Mf9soVZv9wGlrp-g0KIhsp.dZTOwUDLxgDO0czW}
```

## hidden files
```
hacker@commands~hidden-files:~$ cd /                                                                                                                                hacker@commands~hidden-files:/$ ls -a
.  ..  .dockerenv  .flag-707929599742  bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32
media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var 
hacker@commands~hidden-files:/$ cat .flag-707929599742
pwn.college{w6N1bv9uCHf06nGw0jMt-Y9kFxu.dBTN4QDLxgDO0czW}
```

## An Epic Filesystem Quest
```
```

## making directionaries 
First to create `/tmp/pwn` directionary, `cd /tmp` and then `mkdir pwn` <br>
and then `cd pwn` <br>
`/tmp/pwn` is created <br>
giving `touch` command to give 'college' file in it. <br>
run `/challenge/run` to check and obtain flag
```
hacker@commands~ma
king-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{Qw4jCLZ4TUr05wsVbr1n4rfebYR.dFzM4QDLxgDO0czW}
```

## finding files





## linking files
```
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{om_p1c4TOrjywHqsHsktdV2Ug23.dlTM1UDLxgDO0czW}
```




