# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** en una de las pocas cadenas legibles por humanos, precedida por varios caracteres '='.

## Datos de acceso
**Usuario:** bandit9
**Contraseña:** EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solucion
``` shell
ssh bandit9@bandit.labs.overthewire.org -p2220
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$  cat data.txt
//escritos no legibles
bandit9@bandit:~$ strings data.txt
//se ven los escritos pero aun nos dalta buscar la contraseña que tenga =
bandit9@bandit:~$ strings data.txt | grep ==
========== the*2i"4
=:G e
========== password
<I=zsGi
Z)========== is
A=|t&E
Zdb=
c^ LAh=3G
*SF=s
&========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
S=A.H&^

//se sospecha de G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
## Notas adicionales
El comando grep filtra todos los archivos =

## Referencias

## Comandos que puedes necesitar para resolver este nivel
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd