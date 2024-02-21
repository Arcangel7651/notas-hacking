## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel
Usuario: bandir10
Contraseña: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
```
bandit10@bandit:~$ echo "nos vamos de pachanga" | base64
bm9zIHZhbW9zIGRlIHBhY2hhbmdhCg==
bandit10@bandit:~$ echo "nos vamos de pachanga" | base64 | base64 | base64
WW0wNWVrbElXbWhpVnpsNlNVZFNiRWxJUW1oWk1taG9ZbTFrYUVOblBUMEsK
bandit10@bandit:~$ cat
.bash_logout  .bashrc       data.txt      .profile
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
```
## Notas Adicionales
Con " | base64" puedes codificar algun texto(puede deser varias veces)
	Si utilizas -d en el comando base64 descodifica
## Referencias
