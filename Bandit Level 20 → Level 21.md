## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Datos de acceso al nivel
Usuario: bandit20
Contraseña: VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solución
```
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ nc -lnvp 777 <<< "mamala cris"
nc: Permission denied
bandit20@bandit:~$ nc -lnvp 777
nc: Permission denied
bandit20@bandit:~$ nc -lnvp 7777
Listening on 0.0.0.0 7777
^C
bandit20@bandit:~$ nc -lnvp 7777 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 135396
bandit20@bandit:~$ Listening on 0.0.0.0 7777
jobs
[1]+  Running                 nc -lnvp 7777 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ./suconnect 7777
Connection received on 127.0.0.1 41692
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
bandit20@bandit:~$

```
## Notas Adicionales
Linux puede mandar a segundo plano con un &
## Referencias
