## Printing Variables
`echo` command is used to print stuff <br>
The flag was hidden in FLAG variable which can be printed using `echo` command. <br>
A variabe name can be prepended using `$` <br>
So the flag can be achieved by `echo $FLAG`
```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{IaXCnu3TGlNXcE0Za5Nuogw8wgF.ddTN1QDLxgDO0czW}
```

## Setting Variables
`=` is used for reading values stored in variables <br>
The value of variable COLLEGE can be stored in variable PWN by using `=` with no spaces <br>
```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{E-JW2_uK6oOdzvFWY43Gyf43y2d.dlTN1QDLxgDO0czW}
```

## Multi-word Variables
To set up multi-word variables, space around `=` ends the variable assignment and interprets the next word, so we need to quote it. <br>
for setting up COLLEGE YEAH to PWN, we use `PWN="COLLEGE YEAH"`
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QnZm4TWi6TF3rVeVtvMd9nFp_NE.dBjN1QDLxgDO0czW}
```

## Exporting Variables
`export` is used to export variables. When we export our variables, they are passed into the environment variables of child processes <br>
The challenge wants us to export PWN variable and set to the value COLLEGE and also <br>
the COLLEGE variable set to the value PWN but not exported <br>
and then invoke `/challenge/run`
```
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. 
Great job! Here is your flag:
pwn.college{sVT6q2Zv13Sk1tlvkxBO-WHrl4h.dJjN1QDLxgDO0czW}
```
## Printing Exported Variables
`env` command is used to print out every exported variable set in the shell
```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
DOJO_AUTH_TOKEN=c2caaef6779027657b596de4b604da6a0597cb3d95400005600fc531e5383a44
HOME=/home/hacker
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;
41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.
arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;
31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.
lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;
31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.
whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.
mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.
png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;
35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;
35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;
35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.
wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;
90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;
90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:
FLAG=pwn.college{s_Ez_AJoGrzSRtljvDNcjtIMD_F.dhTN1QDLxgDO0czW}
LESSCLOSE=/usr/bin/lesspipe %s %s
TERM=xterm
LESSOPEN=| /usr/bin/lesspipe %s
SHLVL=1
LC_CTYPE=C.UTF-8
PATH=/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/run/workspace/bin/env
```
Finding FLAG in this 
```
FLAG=pwn.college{s_Ez_AJoGrzSRtljvDNcjtIMD_F.dhTN1QDLxgDO0czW}
```

## Storing Command Output
`$()` is used to store the output of some command into a variable
```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out and submit it!
hacker@variables~storing-command-output:~$ echo "$PWN"
pwn.college{w9L6yorV9y_ako1AQYe2TQzd9Ad.dVzN0UDLxgDO0czW}
```

## Reading Inputs
Reading the input using `read` command and `-p` argument, which let's us specify a prompt
```
hacker@variables~reading-input:~$ read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Iv7H8Ka6UZ61vI17y51umwQLY7O.dhzN1QDLxgDO0czW}
```

## Reading Files
```

hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{E8X_z2rm-RaftAjMZI9DyTkIr-s.dBjM4QDLxgDO0czW}
```



