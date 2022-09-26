# Bandit
## Objetivo
Para obtener acceso al siguiente nivel, debe usar el binario setuid en el directorio de inicio. Ejecutarlo sin argumentos para saber cómo usarlo. La contraseña para este nivel se puede encontrar en el lugar habitual (/etc/bandit_pass), después de haber utilizado el binario setuid.

## Datos de acceso
**Usuario:** bandit19
**Contraseña:** awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Solucion
``` shell
ssh bandit19@bandit.labs.overthewire.org -p2220
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rwsr-x---  1 bandit20 bandit19 14872 Sep  1 06:30 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ ./bandit20-do
 Example: ./bandit20-do id
bandit19@bandit:~$./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)

//buscamos el acceso donde podamos entrar
//y buscamos dirigirnos al directorio /etc/bandit_pass

bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
## Notas adicionales

## Referencias
[setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)

## Comandos que puedes necesitar para resolver este nivel
ssh, ls, cat