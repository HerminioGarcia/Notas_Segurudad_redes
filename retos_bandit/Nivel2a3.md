# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **spaces in this filename** ubicado en el directorio de inicio

## Datos de acceso
**Usuario:** bandit2
**Contraseña:** rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solucion
``` shell
ssh bandit2@bandit.labs.overthewire.org -p2220
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
## Notas adicionales
Usa el tabulador para poder completar el nombre

## Referencias
-   [Búsqueda en Google de "nombre de archivo discontinuo"](https://www.google.com/search?q=dashed+filename)
-   [Guía avanzada de secuencias de comandos Bash - Capítulo 3 - Caracteres especiales](http://tldp.org/LDP/abs/html/special-chars.html)

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep