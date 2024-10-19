## Becoming root with su
The `su` command in lets us switch to another user's account or execute commands as a different user.
```
hacker@users~becoming-root-with-su:~$ su
```
before allowing the user to elevate privileges to root, it checks to make sure that the user knows the root password: <br>
`hack-the-planet` (provided password)
```
Password:
```
catting `/flag` to obtain the flag
```
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{4vlTORXaEyYJwfjbixZ4Z9qOSc7.dVTN0UDLxgDO0czW}
```

## Other users with su
The `su` command with a user as an argument allows us to switch to that user.<br>
Here we are switching to user `zardus` with password provided `dont-hack-me`
```
hacker@users~other-users-with-su:~$ su zardus
Password:
```
and then running `/challenge/run` to obtain the flag
```
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{wr0O9lk92IAvl9_OSMG11_5mofX.dZTN0UDLxgDO0czW}
```

## Cracking passwords
`/challenge/shadow-leak` is used to crack the password hash.
```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
```
```
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:03 37% 1/3 0g/s 287.0p/s 287.0c/s 287.0C/s Ozardus99999...zardus
0g 0:00:00:06 69% 1/3 0g/s 287.0p/s 287.0c/s 287.0C/s Z99999E..1z999991
0g 0:00:00:07 76% 1/3 0g/s 287.5p/s 287.5c/s 287.5C/s 9999945..Z9999932
0g 0:00:00:09 93% 1/3 0g/s 284.5p/s 284.5c/s 284.5C/s zardus999992002..zardus1963
0g 0:00:00:11 0% 2/3 0g/s 285.0p/s 285.0c/s 285.0C/s lacrosse..pumpkin
0g 0:00:00:13 0% 2/3 0g/s 285.2p/s 285.2c/s 285.2C/s bigdog..francesco
0g 0:00:00:14 0% 2/3 0g/s 285.4p/s 285.4c/s 285.4C/s serena..88888888
0g 0:00:00:14 0% 2/3 0g/s 285.9p/s 285.9c/s 285.9C/s deedee..grizzly
0g 0:00:00:16 0% 2/3 0g/s 286.3p/s 286.3c/s 286.3C/s rockie..surfing
0g 0:00:00:17 1% 2/3 0g/s 286.6p/s 286.6c/s 286.6C/s pretty..celtic
0g 0:00:00:18 1% 2/3 0g/s 286.7p/s 286.7c/s 286.7C/s chacha..jazmin
0g 0:00:00:19 1% 2/3 0g/s 286.9p/s 286.9c/s 286.9C/s 10sne1..nermal
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04926g/s 286.8p/s 286.8c/s 286.8C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
```
Switching the user to `zardus` with `su` and then entering the password. <br>
The password for `zardus` is `aardvark`
```
hacker@users~cracking-passwords:~$ su zardus
Password:
```
running `/challenge/run` to obtain the flag.
```
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{QCtnRb2i2EL7MGEx06tv1NOzrML.ddTN0UDLxgDO0czW}
```

## Using sudo
`sudo` defaults to running a command as root <br>
This challenge gives us `sudo` permission
```
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{syOuQ_cBqJsm4i5RzsgKMvT6Rh3.dhTN0UDLxgDO0czW}
```
