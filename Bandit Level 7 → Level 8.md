## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Datos de acceso al nivel
Usuario: bandit7
Contraseña: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución
```
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ head data.txt
gallop  hu3ZhCrGRvfaO5jsY6ttvApzVCA2Hjvs
Aurelia's       ikl4F3cK5m6Cl6HAxva6zUAVJhI2Cvc6
stoicism        JiW9ts44udf20bJHe8H5dS1c99Muwz42
embodies        vWheZcAsQHZNnerI3ViW8wqOKIx0kbgR
Plato   dW2U8E5FfuAvNLdGDupP8GAxr922ZV0x
cultivation     A90E75jvWbEKrijFxM4GxqHEw8c8U2Bf
stable  omR4PHolFwbI0IEJsanveA21yWvFy8a7
bedspread       VlBFxuEDi3phEpljbKbahRJvJxfh3k9M
oppressing      hQTiEm5XF3cUQSEiBjh7sekemLOKBrcJ
darnedest       9O2zdCLKVoW5u34P9T7EKTZXcMRE6xh5
bandit7@bandit:~$ tail data.txt
bookkeeping     3qCNwJCGR6esdjIgCyyubIDYuZG8YTIb
coarsen yeQFtsspdMHS4lZKwmJG6Oes6JZpvEYk
methanol        q0uEpjSocMpf4TaHo78t8E2Bsc1uTOcK
Formica mo0dVnMSPCo9WdHItXLHMeD0w6SqbMvF
dankness's      YOdD93vvBemBnw7xH0XNKUwPkEfpe7H7
threaten        pOaRPotuhqaf7d9lM0chKcHSM5xQ23qU
monastic        HmNtOzjzjVBHmoKRMH2CMArixJtnt5X3
flank's 234YYMFvjRGfWFZeVlijZAoSaDJSZR3m
demarcates      42GyLcNN2VyYVQAzLk6lH1KoPF7gU60v
biceps's        InBCsYpHT8o1atjygiRFnVE2ExoyirYv
bandit7@bandit:~$ wc -l data.txt
98567 data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
```
## Notas Adicionalesç
head: muestra las primeras lineas de un archivo
tail: muestra las ultimas lineas de un archivo
wc: cuenta las lineas de un archivo
grep: filtra en base a un patron
## Referencias
