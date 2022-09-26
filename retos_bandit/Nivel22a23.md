# Bandit
## Objetivo
Un programa se ejecuta automáticamente a intervalos regulares desde **cron** , el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y vea qué comando se está ejecutando.

**NOTA:** Mirar scripts de shell escritos por otras personas es una habilidad muy útil. El guión para este nivel se hace fácil de leer intencionalmente. Si tiene problemas para comprender lo que hace, intente ejecutarlo para ver la información de depuración que imprime.

## Datos de acceso
**Usuario:** bandit22
**Contraseña:** WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

## Solucion

``` shell
ssh bandit22@bandit.labs.overthewire.org -p2220
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

bandit22@bandit:~$ ls -la /etc/cron.d
total 48
drwxr-xr-x   2 root root 4096 Sep  1 06:30 .
drwxr-xr-x 110 root root 4096 Sep  8 12:09 ..
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit15_root
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit17_root
-rw-r--r--   1 root root  120 Sep  1 06:30 cronjob_bandit22
-rw-r--r--   1 root root  122 Sep  1 06:30 cronjob_bandit23
-rw-r--r--   1 root root  120 Sep  1 06:30 cronjob_bandit24
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit25_root
-rw-r--r--   1 root root  201 Jan  8  2022 e2scrub_all
-rwx------   1 root root   52 Sep  1 06:30 otw-tmp-dir
-rw-r--r--   1 root root  102 Mar 23 13:49 .placeholder
-rw-r--r--   1 root root  396 Feb  2  2021 sysstat
bandit22@bandit:~$ cat /etc/cron.d/^C
bandit22@bandit:~$ cronjob_bandit23
cronjob_bandit23: command not found
bandit22@bandit:~$
bandit22@bandit:~$
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget

bandit22@bandit:~$ whoami
bandit22
bandit22@bandit:~$ myname=bandit23
//cambiamos el myname por el bandit23
bandit22@bandit:~$ echo $myname
bandit23
bandit22@bandit:~$ mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
//corremos el mytarget pero ya on el myname cambiado
bandit22@bandit:~$ echo $mytarget
//vrmos en el archivo que no lo guardo
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
//nos dirijimos y vemos el contenido
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
## Notas adicionales
Usando cat /usr/bin/cronjob banti23.sh podemos ver que es un script que toma un parámetro.
Podemos cambiar las variables.

## Referencias

## Comandos que puedes necesitar para resolver este nivel
cron, crontab, crontab(5) (use “man 5 crontab” to access this)
