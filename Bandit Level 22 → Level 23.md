## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Datos de acceso al nivel
Usuario: bandit22
Contraseña: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

## Solución
```
bandit22@bandit:~$ ls /etc/cron.d/
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo "I am bandit23 |md5sum | cut -d ' ' -f 1"
I am bandit23 |md5sum | cut -d ' ' -f 1
bandit22@bandit:~$ echo "I am bandit23 | md5sum | cut -d ' ' -f 1"
I am bandit23 | md5sum | cut -d ' ' -f 1
bandit22@bandit:~$ echo "I am bandit23" | md5sum | cut -d ' ' -f 1
d7387859980fe85c84d68d50eedd8598
bandit22@bandit:~$ cat /tmp/d7387859980fe85c84d68d50eedd8598
cat: /tmp/d7387859980fe85c84d68d50eedd8598: No such file or directory
bandit22@bandit:~$ echo "I am user bandit23" | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$
```
## Notas Adicionales
## Referencias
