## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Datos de acceso al nivel
Usuario: bandit12
Contraseña: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solución
Solución difícil
```
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ mkdir /tmp/20201000
bandit12@bandit:~$ cp /tmp/20201000
cp: missing destination file operand after '/tmp/20201000'
Try 'cp --help' for more information.
bandit12@bandit:~$ cp
.bash_logout  .bashrc       data.txt      .profile
bandit12@bandit:~$ cp tmp
cp: missing destination file operand after 'tmp'
Try 'cp --help' for more information.
bandit12@bandit:~$ cd /tmp/20201000
bandit12@bandit:/tmp/20201000$ xxd -r ~/data.txt > data
bandit12@bandit:/tmp/20201000$ ls
data
bandit12@bandit:/tmp/20201000$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/20201000$ mv data data.gz
bandit12@bandit:/tmp/20201000$ gzip -d data.gz
bandit12@bandit:/tmp/20201000$ ls
data
bandit12@bandit:/tmp/20201000$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/20201000$ mv data data.bz2
bandit12@bandit:/tmp/20201000$ ls
data.bz2
bandit12@bandit:/tmp/20201000$ bzip2 -d data.bz2
bandit12@bandit:/tmp/20201000$ ls
data
bandit12@bandit:/tmp/20201000$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/20201000$ mv data data.gz
bandit12@bandit:/tmp/20201000$ ls
data.gz
bandit12@bandit:/tmp/20201000$ gzip -d data.gz
bandit12@bandit:/tmp/20201000$ ls
data
bandit12@bandit:/tmp/20201000$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/20201000$ tar -d data.tar
tar: Refusing to read archive contents from terminal (missing -f option?)
tar: Error is not recoverable: exiting now
bandit12@bandit:/tmp/20201000$ mv data data.tar
bandit12@bandit:/tmp/20201000$ ls
data.tar
bandit12@bandit:/tmp/20201000$ tar xf data.tar
bandit12@bandit:/tmp/20201000$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/20201000$ rm data.tar
bandit12@bandit:/tmp/20201000$ ls
data5.bin
bandit12@bandit:/tmp/20201000$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/20201000$ mv data5.bin data5.tar
bandit12@bandit:/tmp/20201000$ ls
data5.tar
bandit12@bandit:/tmp/20201000$ tar xf data5.tar
bandit12@bandit:/tmp/20201000$ ls
data5.tar  data6.bin
bandit12@bandit:/tmp/20201000$ rm data5.tar
bandit12@bandit:/tmp/20201000$ ls
data6.bin
bandit12@bandit:/tmp/20201000$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/20201000$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/20201000$ ls
data6.bz2
bandit12@bandit:/tmp/20201000$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/20201000$ ls
data6
bandit12@bandit:/tmp/20201000$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/20201000$ mv data6 data6.tar
bandit12@bandit:/tmp/20201000$ ls
data6.tar
bandit12@bandit:/tmp/20201000$ tar xf data6.tar
bandit12@bandit:/tmp/20201000$ ls
data6.tar  data8.bin
bandit12@bandit:/tmp/20201000$ rm data
data6.tar  data8.bin
bandit12@bandit:/tmp/20201000$ rm data6.tar
bandit12@bandit:/tmp/20201000$ ls
data8.bin
bandit12@bandit:/tmp/20201000$ mv data8.bin data8.gz
bandit12@bandit:/tmp/20201000$ ls
data8.gz
bandit12@bandit:/tmp/20201000$ file data8.gz
data8.gz: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/20201000$ gzip -d data8.gz
bandit12@bandit:/tmp/20201000$ ls
data8
bandit12@bandit:/tmp/20201000$ file data8
data8: ASCII text
bandit12@bandit:/tmp/20201000$ car data8
Command 'car' not found, but can be installed with:
apt install ucommon-utils
Please ask your administrator.
bandit12@bandit:/tmp/20201000$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

Solución  Fácil
```
bandit12@bandit:~$
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat |file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat | tar xO |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat | tar xO | tar xO |file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat | tar xO | tar xO| bzcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat | tar xO | tar xO| bzcat | tar xO |file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat | tar xO | tar xO| bzcat | tar xO| zcat |file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat| zcat | tar xO | tar xO| bzcat | tar xO| zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

Resultado: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
## Notas Adicionales
Vaciado hexadecimal:
```
00000000: 1f8b 0808 6855 1e65 0203 6461 7461 322e  ....hU.e..data2.
00000010: 6269 6e00 013d 02c2 fd42 5a68 3931 4159  bin..=...BZh91AY
00000020: 2653 5948 1b32 0200 0019 ffff faee cff7  &SYH.2..........
```

xxd: realiza un vaciado hexadecimal.

.gz gzip -d Dificil
	zcat facil
.bzz bzip -d
	bzcat
.tar tar xf
	tar xO

mv: puedes cambiar el nombre del archivo
## Referencias
