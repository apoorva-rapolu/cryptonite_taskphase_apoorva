## Chaining with Semicolons
`;` is used to seperate commands <br>
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{4tFc-lycyqhZVUVpI4_lUM6HakI.dVTN4QDLxgDO0czW}
```

## Your First Shell Script
When the length of the command prompt increases too much, <br>
we can put these commands in a file, called a shell script, and run them by executing the file. <br>
shell scripts are frequently named with a sh suffix <br>
here we are creating a `x.sh` shell script to store the commands `/challenge/pwn` and `/challenge/college` <br>
and execute these commands by ececuting the file with `bash`

```
hacker@chaining~your-first-shell-script:~$ echo "/challenge/pwn;/challenge/college">x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{UBVGBzuuqzjzkhvTS9mcZ_rirYy.dFzN4QDLxgDO0czW}
```

## Redirecting shell script
Same as before, storing the commands in shell script `x.sh`
```
hacker@chaining~redirecting-script-output:~$ echo "/challenge/pwn;/challenge/college">x.sh
```
and then, piping the output of the script into a single invocation of the `/challenge/solve` command.
```
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{8qpjDMuQkzgHcilxu5qx3-pHyAC.dhTM5QDLxgDO0czW}
```

## Executable shell scripts
Creating a shell script `x.sh` and then storing the command `/challenge/solve` in it :
```
hacker@chaining~executable-shell-scripts:~$ touch x.sh
hacker@chaining~executable-shell-scripts:~$ echo "/challenge/solve">x.sh
```
Giving the user (`u`) executive permissions (`x`) for the file `x.sh` using `chmod u+x x.sh`
```
hacker@chaining~executable-shell-scripts:~$ chmod u+x x.sh
```
and then running the file without bash
```
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{soED5cmKzN20S9GGdfgPyEHPsTS.dRzNyUDLxgDO0czW}
```
