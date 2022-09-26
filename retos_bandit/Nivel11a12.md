# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** , donde todas las letras minúsculas (az) y mayúsculas (AZ) se han girado 13 posiciones

## Datos de acceso
**Usuario:** bandit11
**Contraseña:** 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solucion
``` shell
ssh bandit11@bandit.labs.overthewire.org -p2220
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z][n-za-nN-ZA-N]
tr: missing operand after ‘[a-zA-Z][n-za-nN-ZA-N]’
Two strings must be given when translating.
Try 'tr --help' for more information.
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
## Notas adicionales
Podemos desifrar la contraseña con el siguiente comando cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]

## Referencias
https://en.wikipedia.org/wiki/Rot13

## Comandos que puedes necesitar para resolver este nivel
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd