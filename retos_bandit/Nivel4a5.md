# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el único archivo legible por humanos en el directorio **inhere** . Consejo: si su terminal está desordenada, intente con el comando "restablecer".

## Datos de acceso
**Usuario:** bandit4
**Contraseña:** pIwrPrtPN36QITSp3EQaw936yaFoFgAB

## Solucion
ssh bandit4@bandit.labs.overthewire.org -p2220
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat < -file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## Notas adicionales
Con el comando ./* podemos ver todos los arcivos file que puedan ser legibles para los humanos

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep
