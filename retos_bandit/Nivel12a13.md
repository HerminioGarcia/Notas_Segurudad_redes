# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** , que es un volcado hexadecimal de un archivo que ha sido comprimido repetidamente. Para este nivel, puede ser útil crear un directorio bajo /tmp en el que pueda trabajar usando mkdir. Por ejemplo: mkdir /tmp/myname123. Luego copie el archivo de datos usando cp, y cámbiele el nombre usando mv (¡lea las páginas de manual!)

## Datos de acceso
**Usuario:** bandit12
**Contraseña:** JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solucion
ssh bandit12@bandit.labs.overthewire.org -p2220
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 May  7  2020 .
drwxr-xr-x 41 root     root     4096 May  7  2020 ..
-rw-r--r--  1 root     root      220 May 15  2017 .bash_logout
-rw-r--r--  1 root     root     3526 May 15  2017 .bashrc
-rw-r-----  1 bandit13 bandit12 2582 May  7  2020 data.txt
-rw-r--r--  1 root     root      675 May 15  2017 .profile
bandit12@bandit:~$ cat data.txt | xxd -r | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Notas adicionales
Podemos desifrar la contraseña con xxd -r y podemos usar zcat, bzcat y tar xO para ver la contraseña

## Referencias
https://en.wikipedia.org/wiki/Hex_dump

## Comandos que puedes necesitar para resolver este nivel
grep, ordenar, uniq, instrumentos de cuerda, base64, tr, alquitrán, gzip, bzip2, xxd, mkdir, cp, mv, archivo

