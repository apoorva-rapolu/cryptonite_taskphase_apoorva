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
