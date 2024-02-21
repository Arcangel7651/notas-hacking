## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de acceso al nivel
Usuario: bandit11
Contraseña: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
```
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

## Notas Adicionales
ROT13: Mueve la posicion de una letra 13 veces de a-m n-z
El comando tr transforma una codena
## Referencias
https://en.wikipedia.org/wiki/ROT13