## Objetivo
The password for the next level is stored in a file called **-** located in the home directory
## Datos de acceso al nivel
Usuario: bandit1
Contraseña: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL


## Solución
#Primer_intento
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$
```
#Segundo_intento_final
```
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi


bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
## Notas Adicionales
Si quieres referenciar archivos que tengan un simbolo como nombre, usar ./(el '.' se refiere a la carpeta actual) antes dle nombre para referenciar el archivo, o poner la ruta del archivo
## Referencias
https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal