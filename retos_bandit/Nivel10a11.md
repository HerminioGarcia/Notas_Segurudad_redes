# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** , que contiene datos codificados en base64

## Datos de acceso
**Usuario:** bandit10
**Contraseña:** G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solucion
``` shell
ssh bandit10@bandit.labs.overthewire.org -p2220
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

// otro metodo

bandit10@bandit:~$ python
import codecs
data= open ('data.txt','r').read()
data
'VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg= = \n'
codecs.decode(data,'base64')
'The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM\n'
```
## Notas adicionales
Con base64 -d podemos desifrar la codificasion de base64

## Referencias
https://en.wikipedia.org/wiki/Base64

## Comandos que puedes necesitar para resolver este nivel
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd