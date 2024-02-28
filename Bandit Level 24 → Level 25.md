## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
## Datos de acceso al nivel
Usuario: bandit24
Contraseña: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solución
```
bandit24@bandit:/tmp/tmp.mfo6hfMap5$ nano brute_force_pin.sh
Unable to create directory /home/bandit24/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit24@bandit:/tmp/tmp.mfo6hfMap5$ ./brute_force_pin.sh
bandit24@bandit:/tmp/tmp.mfo6hfMap5$ ls
brute_force_pin.sh  possibilities.txt  result.txt
bandit24@bandit:/tmp/tmp.mfo6hfMap5$ sort result.txt | grep -v "Wrong!"

Correct!
Exiting.
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

```

en el scrip
```
```bash
#!/bin/bash

for i in {0000..9999}
do
        echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i >> possibilities.txt
done

cat possibilities.txt | nc localhost 30002 > result.txt
```
## Notas Adicionales
## Referencias
