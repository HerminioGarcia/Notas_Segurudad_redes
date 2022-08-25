# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio **inhere** .

## Datos de acceso
**Usuario:** bandit3
**Contraseña:** UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

## Solucion
ssh bandit3@bandit.labs.overthewire.org -p2220
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB


## Notas adicionales
Para ver los archivos oculros usa ls -a

## Referencias
