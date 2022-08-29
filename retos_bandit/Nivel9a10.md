# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** en una de las pocas cadenas legibles por humanos, precedida por varios caracteres '='.

## Datos de acceso
**Usuario:** bandit9
**Contraseña:** UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Solucion
ssh bandit9@bandit.labs.overthewire.org -p2220
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$  cat data.txt
//escritos no legibles
bandit9@bandit:~$ strings data.txt
//se ven los escritos pero aun nos dalta buscar la contraseña que tenga =
bandit9@bandit:~$ strings data.txt | grep =
========== the*2i"4
=:G e
========== password
<I=zsGi
Z)========== is
A=|t&E
Zdb=
c^ LAh=3G
*SF=s
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
S=A.H&^

//se sospecha de truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## Notas adicionales
El sort sive para ordenar todos los archivos, con uniq buscamos la contraseña que no se repite

## Referencias

## Comandos que puedes necesitar para resolver este nivel
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd