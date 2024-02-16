## Objetivo
## Datos de acceso al nivel
Usuario: bandit5
Contraseña: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Solución
```
bandit5@bandit:~/inhere$ find . -readable  -size 1033c -type f
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Notas Adicionales
find: te sirve para encontrar un archivo
	-readable solo archivos que se puedan ser legibles
	-size: el tamaño que debe de tener el archivo
		-c es el tamañp en bites lo pones al final de la cantidad (cada letra representar en que medida puedes usarla)
	-type: un tipo de archivo
		-f: tipo de archivo normal
## Referencias
https://man7.org/linux/man-pages/man1/find.1.html