## The PATH Variable
```
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{s9i0vUdt6DRwkfsUwE5Hh8ZuU-K.dZzNwUDLxgDO0czW}
```

## Setting PATH
PATH stores a list of directories to find commands in and, <br>
for commands in nonstandard places, we must typically execute them via their path <br>
setting the PATH
```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
```
and then running `/challenge/run`
```
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{UfpGzsR2xrftlymh_3U_-ixnF4n.dVzNyUDLxgDO0czW}
```

## Adding Commands
Creating `win` file and storing `'cat /flag'` in `win` and then setting the path <br>
```
hacker@path~adding-commands:~$ touch win
hacker@path~adding-commands:~$ echo 'cat /flag'>win
hacker@path~adding-commands:~$ PATH="/home/hacker:$PATH"
```
Giving executive access to everyone using `chmod a+x`
```
hacker@path~adding-commands:~$ chmod a+x win
```
and then running `/challenge/run`
```
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{k6abK_Ts2BfJihnyfboSM0CeBcY.dZzNyUDLxgDO0czW}
```

## Hijacking Commands

this challenge will delete the flag using the `rm` command <br>
By creating a file called `rm`, this file I created will be executed instead of the command <br>
and flag won't be deleted.
Creating `rm` file and storing `'cat /flag'` in `rm` and then setting the path <br>
```
hacker@path~hijacking-commands:~$ touch rm
hacker@path~hijacking-commands:~$ echo 'cat /flag'>rm
hacker@path~hijacking-commands:~$ PATH="/home/hacker:$PATH"
```
Giving executive access to everyone 
```
hacker@path~hijacking-commands:~$ chmod a+x rm
```
and then running `/challenge/run` to get that flag!
```
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
pwn.college{M8ib9eXc8-Bn0jnedKBdHQ4vfGC.ddzNyUDLxgDO0czW}
```
