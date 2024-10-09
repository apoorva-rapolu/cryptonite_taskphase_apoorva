## Redirecting output
using `echo` and `>` to redirect the word PWN to the filename COLLEGE
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your flag:
pwn.college{oRAFxbomJp3wPTV1AvdbbGsaVx2.dRjN1QDLxgDO0czW}
```

## Redirecting more output
```
hacker@piping~redirecting-more-output:~$ /challenge/run > my flag
```
```
hacker@piping~redirecting-more-output:~$ cat myflag
[FLAG] Here is your flag:
[FLAG] pwn.college{kZNaobhQm71rwhrIrv8pHJNS2uz.dVjN1QDLxgDO0czW}
```

## Appending output
```
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
hacker@piping~appending-output:~$ echo stdout >> /home/hacker/the-flag
hacker@piping~appending-output:~$ cat /home/hacker/the-flag 
pwn.college{A7UHKff8n4kthktFlPOwBJ9nTHA.ddDM5QDLxgDO0czW}
```

## Redirecting errors
```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag
[FLAG] Here is your flag:
[FLAG] pwn.college{Y1vvJ_QTI6aCbPup_lbjgTToWhO.ddjN1QDLxgDO0czW} 
```
## Redirecting inputs
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:                                                                                                      pwn.college{cSzUCUQAPVkSXquwg486wFufgQS.dBzN1QDLxgDO0czW}
```

## Grepping stored results
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
```
grepping `pwn.coolege` for flag
```
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{ciNelIQzNW_4RueeTVR0G0f4N35.dhTM4QDLxgDO0czW}
```

## Grepping live outputs
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
```
```
pwn.college{EwSSdajCOoWZFCynBFQes7TGbCB.dlTM4QDLxgDO0czW}
```
## Grepping errors
```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
```
```
pwn.college{UOlPicRdobrjCiunsCM-rCbZMub.dVDM5QDLxgDO0czW}
```

## Duplicating piped data with tee
```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee myflag | /challenge/college
```
```
hacker@piping~duplicating-piped-data-with-tee:~$ cat myflag
Usage: /challenge/pwn --secret [SECRET_ARG]
```
```
SECRET_ARG should be "Ukpi0gL9"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret Ukpi0gL9 | /challenge/college
```
```
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{Ukpi0gL9poFRbPjcVD0AmmXAduX.dFjM5QDLxgDO0czW}  
```

## Writing to multiple programs
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack |tee >(/challenge/the) | /challenge/planet
Congratulations, you have duplicated data into the input of two programs!
Here is your flag:
pwn.college{0SpIvqi8aaS79XCl3WP7mnnwyNN.dBDO0UDLxgDO0czW}
```

## Split-piping stderr and stdout
```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{U9Yj_g_yv6NavByqWfey3rl7Um2.dFDNwYDLxgDO0czW}
```



