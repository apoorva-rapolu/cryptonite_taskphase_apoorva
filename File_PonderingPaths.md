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


## Implicit relative paths
> **flag** : 






