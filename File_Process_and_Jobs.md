## Listing Process
`ps` either stands for "process snapshot" or "process status", and it lists processes. By default, ps just lists the processes running in the terminal. <br>
`-e` is used to list "every" process and `-f` for a "full format" output, including arguments. These can be combined into a single argument `-ef` <br>
Now we need to out the filename to which `/challenge/run` is renamed to, and relaunch it directly for the flag.
```
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 09:47 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 09:47 ?        00:00:00 /run/dojo/bin/sleep 6h
root          68       1  0 09:47 ?        00:00:00 /challenge/27861-run-11610
root          72      68  0 09:47 ?        00:00:00 sleep 6h
hacker        73       0  0 09:47 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        90       0  0 09:47 pts/1    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       107      90  0 09:47 pts/1    00:00:00 ps -ef
hacker@processes~listing-processes:~$  /challenge/27861-run-11610
Yahaha, you found me! Here is your flag:
pwn.college{cxSEhSFLdmfDL79UEJTVh0420U1.dhzM4QDLxgDO0czW}
```

## Killing Process
`sleep` is a program that simply hangs out for the number of seconds specified on the commandline
```
hacker@processes~killing-processes:~$ ps -e | grep sleep
74 ?        00:00:00 sleep
```
In this case it's 72 seconds <br>
We use `kill` to terminate it by passing the process identifier `ps` as an argument
```
hacker@processes~killing-processes:~$ kill 74
hacker@processes~killing-processes:~$ ps -e | grep sleep
```
and then run `/challenge/run`
```
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{gyk919Blb2FL-tEyLexEaytwNrn.dJDN4QDLxgDO0czW}
```

## Interrupting Processes
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits.
Remember, you can force me to exit with Ctrl-C. Try it now!
^C
```
`Ctrl-C` (Ctrl key + C) sends an "interrupt" to whatever application is waiting on input from the terminal and, typically, this causes the application to cleanly exit.
```
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{cVAjbXjFPevhqS64prSKB6ysQmf.dNDN4QDLxgDO0czW}
```

## Suspending Processes
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!                                                                                                                                                                                                                                                                                                                                                                                                         UID          PID    PPID  C STIME TTY          TIME CMD
root          99      71  0 10:05 pts/1    00:00:00 bash /challenge/run
root         101      99  0 10:05 pts/1    00:00:00 ps -f
I don't see a second me!
To pass this level, you need to suspend me and launch me again!
You can background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
```
We can suspend processes to the background with `Ctrl-Z` <br>
This challenge wants us to see another copy of itself running and <br>
using the same terminal by launching it, then suspending it, then <br>
launching another copy while the first is suspended.
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!
UID          PID    PPID  C STIME TTY          TIME CMD
root          99      71  0 10:05 pts/1    00:00:00 bash /challenge/run
root         106      71  0 10:05 pts/1    00:00:00 bash /challenge/run
root         108     106  0 10:05 pts/1    00:00:00 ps -f
Yay, I found another version of me! Here is the flag:
pwn.college{wc9roBrzqv9VnPGUjHy9zk7mCW5.dVDN4QDLxgDO0czW}
```
## Resuming Processes
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
```
This challenge wants us to suspend process using (ctrl+z), resume it using `fg`
```
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{sYjYAFaNYBi86VD0vXdxteWoJgP.dZDN4QDLxgDO0czW}
```

## Backgrounding Process
Same as before one but we use `bg` command to resume processes in the background <br>
instead of resuming processes in the foreground with the `fg` command.
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!
UID          PID STAT CMD
root         116 S+   bash /challenge/run
root         118 R+   ps -o user=UID,pid,stat,cmd
I don't see a second me!
To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!
UID          PID STAT CMD
root         116 S    bash /challenge/run
root         126 S    sleep 6h
root         127 S+   bash /challenge/run
root         129 R+   ps -o user=UID,pid,stat,cmd
Yay, I found another version of me running in the background! Here is the flag:
pwn.college{89OdGzf9IU4CDkBztlSokFKB05w.ddDN4QDLxgDO0czW}
```

## Foregrounding Process
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!
pwn.college{U8NYqXyySnYpZ1c5DHto1rP9aMo.dhDN4QDLxgDO0czW}
```

## Starting Background Processes
By using `&` command, we can start the backgrounded without suspending processes to background them.
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 102


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...
hacker@processes~starting-backgrounded-processes:~$
Anyways! Here is your flag!
pwn.college{Qtihdg5TpZ9AdpjrbA-ZePA7VeU.dlDN4QDLxgDO0czW}
```

## Process Exit Codes

```
hacker@processes~process-exit-codes:~$ echo $?
40
```
retrieving the exit code returned by `/challenge/get-code` and then running `/challenge/submit-code` with that error code (in this case 40) as an argument.
```
hacker@processes~process-exit-codes:~$ /challenge/submit-code 40
CORRECT! Here is your flag:
pwn.college{QXAzrU9pQ8-kKcEXwgEnqIaHqvu.dljN4UDLxgDO0czW}
```



