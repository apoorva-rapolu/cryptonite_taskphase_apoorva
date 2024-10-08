## Learning From Documentation
straight from the instructions
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{UfPSCjY-VbDeNKohlAcZmMI6Fzu.dRjM5QDLxgDO0czW}
```

## Learning Complex Usage
```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile
You must pass a file for --printfile to read! 
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{UtZMuagbK2sl-KSNFtR9CNir666.dVjM5QDLxgDO0czW}
```

## Reading Manuals
using the `man` command on 'challenge'
```
hacker@man~reading-manuals:~$ man challenge
CHALLENGE(1)
Challenge Commands                                     CHALLENGE(1)
NAME
/challenge/challenge - print the flag!
SYNOPSIS
challenge OPTION
DESCRIPTION
Output the flag when called with the right arguments.
--fortune
read a fortune
--version
output version information and exit
--qovafe NUM
print the flag if NUM is 414
AUTHOR
Written by Zardus.
REPORTING BUGS
The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>  
```
 name is given as `/challenge/challenge` and from reading the description
```
hacker@man~reading-manuals:~$ /challenge/challenge --qovafe 414
Correct usage! Your flag: pwn.college{AO4q146oLSv9aYfeWWkWwATGfHF.dRTM4QDLxgDO0czW}
```
## searching manuals
```
hacker@man~searching-manuals:~$ man challenge
```
this gave me a manual <br>
by using `/flag` and `n` for forward and `N` for backward, in the manual we find the correct argument 
```
 --vrn  This argument will give you the flag!
```
```
hacker@man~searching-manuals:~$ /challenge/challenge --vrn
Initializing...
Correct usage! Your flag: pwn.college{kPm_wHtCJb49TsODjgX2k1_Y6vO.dVTM4QDLxgDO0czW}
```

## searching for manuals

## Helpful Programs
```
hacker@man~helpful-programs:~$ /challenge/challenge --help
```
using this gives the manual
```
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
optional arguments:
-h, --help           show this help message and exit
--fortune             read your fortune
-v, --version         get the version number
-g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                    get the flag, if given the correct value
-p, --print-value     print the value that will cause the -g option to give you the flag
```
on using the info from manual,
```
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 824
hacker@man~helpful-programs:~$ /challenge/challenge -g 824
Correct usage! Your flag: pwn.college{8X-hlfNvLU2wWLOXBxKenECnjed.ddjM4QDLxgDO0czW}
```

## Help for builtins
using `help` command to get manual for `challenge`
```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
This builtin command will read you the flag, given the right arguments!
Options:
--fortune         display a fortune
--version         display the version
--secret VALUE    prints the flag, if VALUE is correct
You must be sure to provide the right value to --secret. That value is "Y7rpbJCP".
```
from manual, it is given that `--secret` should be provided with `Y7rpbJCP`
```
hacker@man~help-for-builtins:~$ challenge --secret Y7rpbJCP
Correct! Here is your flag!
pwn.college{Y7rpbJCPiFBVs6wP9GgAkH_k8El.dRTM5QDLxgDO0czW}
```



