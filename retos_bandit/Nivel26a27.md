# Bandit
## Objetivo
¡Buen trabajo consiguiendo una concha! ¡Ahora date prisa y obtén la contraseña para bandit27!

## Datos de acceso
**Usuario:** bandit26
**Contraseña:** p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solucion

``` shell
ssh bandit26@bandit.labs.overthewire.org -p2220
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

Connection to bandit.labs.overthewire.org closed.
//Recuerda que el bandit26 no te permitira entrar al servidor asi que aplicamos lo mismo que en el reto anterior

//teniendo la pantalla pequeña apretamos v y ponemos lo sigiente

v

:set shell=/bin/bash

:shell
//esto nos permitira entrat

bandit26@bandit:~$ ls -la
total 44
drwxr-xr-x  3 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rwsr-x---  1 bandit27 bandit26 14872 Sep  1 06:30 bandit27-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .ssh
-rw-r-----  1 bandit26 bandit26   258 Sep  1 06:30 text.txt
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27

YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

```
## Notas adicionales
Recordemos que hay servidores que ya no nos permiten entrar desde el inicio asi que devemos buscar la forma para bugear los mensajes de entrada para obtener los datos desde ahi.

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ls