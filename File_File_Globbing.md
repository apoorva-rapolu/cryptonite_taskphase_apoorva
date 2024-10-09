## Matching with *
```
hacker@globbing~matching-with-:~$ cd /challenge*
You specified the path to 'cd' to in more than 4 characters. Disallowed!
This challenge resets your working directory to /home/hacker unless you change directory properly...
```
It is specified that we use only 4 characters <br>
so  using `/ch*` instead and then running it using `/challenge/run`
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{YVcEN-onLgA9Z2-wopQmwbOLb2R.dFjM4QDLxgDO0czW}
```

## Matching with ?
using the `?` character instead of c and l in the argument to `cd`
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{wJzi0kuYjZejpIRVWUjwZ-2nmKF.dJjM4QDLxgDO0czW}
```

## Matching with []
Changing working directory to `/challenge/files`
```
hacker@globbing~matching-with-:~$ cd /challenge/files
```
and then running `/challenge/run` with a single argument that bracket-globs into `file_b`, `file_a`, `file_s`, and `file_h`
```
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{UU7GbhDz-avywFlgZ2qJbv-4AIB.dNjM4QDLxgDO0czW}
```

## Matching paths with []
same as previous but operating from `home/hacker`
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{Ay3iZll0vAwPlrscfujrwWecUyU.dRjM4QDLxgDO0czW}
```

## Mixing globs
```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!                                                                                                            pwn.college{A0javh7IwnPO5RrIH_2Wq17I3l7.dVjM4QDLxgDO0czW}
```

## Exclusionary globbing
same as previous one but using `!` to match the characters that are'nt 'p' ,'w' or 'n'
```
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{Ia69AVCj75hEHrYMi67mQVES8wn.dZjM4QDLxgDO0czW} 
```




