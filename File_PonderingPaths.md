## The Root <br>
> **flag**: pwn.college{U2pmX_23RhljngxNBJAK4Yc-GIA.dhzN5QDLxgDO0czW} <br>

It was given in the exaple itself <br>
starting from "/", path would be "/pwn"


## Program and absolute paths <br>
>**flag**: pwn.college{ErJyVykwg8pGwWoJVyKyprAp-oC.dVDN1QDLxgDO0czW} <br>

It was given "challenge" was in "/" directionary and "run" was in "challenege" directionary <br>
So, from previous challenge I figured out that the path should be /challenge/run.


## Position thy self
> **flag**: pwn.college{gFoDU7pQb-CUjqBpsyMuBJJCrJJ.dZDN1QDLxgDO0czW}

Tried running /challenge/run , it gave <br>
>Incorrect... <br>
You are not currently in the / directory. <br>
Please use the `cd` utility to change directory appropriately. <br>
So invoked '/' directioray by using 'cd' and then gave '/challenge/run'.


## Position elsewhere
> **flag** : pwn.college{glAe-BbGCwNDFFqZesXVE7tHnXu.ddDN1QDLxgDO0czW}

Tried running /challeneg/run, it gave 
> Incorrect... <br>
You are not currently in the /usr/share/doc/fontconfig directory. <br>
Please use the `cd` utility to change directory appropriately. <br>
So invoked '/usr/share/doc/fontconfig' directory bu using 'cd' and then gave '/challenge/run'.


## Position yet elsewhere
> **flag** : pwn.college{EdWWSgl2730YWWZ29Q0IRhlTB3C.dhDN1QDLxgDO0czW} <br>

Tried running /challenge/run , it gave <br>
> Incorrect...  <br>
You are not currently in the /usr/bin directory. <br>
Please use the `cd` utility to change directory appropriately. <br>

So invoked '/usr/bin' directioray by using 'cd' and then gave '/challenge/run'.


## Implicit relative paths, from /
> **flag** : pwn.college{QlDWe61-3pykQJVYJXikgD9gFAm.dlDN1QDLxgDO0czW}

Tried running /challeneg/run, it gave
> Incorrect... <br?
You are not currently in the / directory. <br>
Please use the `cd` utility to change directory appropriately. <br>

So invoked '/' directory by using 'cd' <br>
from the example I figured out that if my cwd is '/', my relative path should be 'challenge/run'.


## Explicit relative paths, from /
>**flag** : pwn.college{wtc4e0McYDyBPB9Kx_jVq29Bw21.dBTN1QDLxgDO0czW}

So invoked '/' directory bu using 'cd' <br>
 my cwd is '/', my relative path should be 'challenge/run', but it gave : <br>
 >Incorrect... <br>
This challenge must be called with a relative path that explicitly starts with a `.`! <br>

so then I gave '. /challenge/run'

## Implicit relative path

>**flag** : pwn.college{sB7Lskt2RdLfQYef9XN33wIkma7.dFTN1QDLxgDO0czW}

first gave a command cd /challenge to invoke challenge directionary <br>
then gave ./run to explicitily want to execte the program in current directionary <br>
>Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:


## home sweet home

invoking /challenge/run by providing absolute path '~/r' (not more than 3 characters) <br>
>Writing the file to /home/hacker/w! <br>
... and reading it back to you: <br>
pwn.college{EE-3UI8r0UspJdYQFuFY6fgD1mt.dNzM4QDLxgDO0czW}









