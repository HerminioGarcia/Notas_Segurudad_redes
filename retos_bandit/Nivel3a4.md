# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio **inhere** .

## Datos de acceso
**Usuario:** bandit3
**Contraseña:** aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solucion
ssh bandit3@bandit.labs.overthewire.org -p2220
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe


## Notas adicionales
Para ver los archivos oculros usa ls -a

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep
