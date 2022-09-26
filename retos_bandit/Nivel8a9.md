# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** y es la única línea de texto que aparece una sola vez

## Datos de acceso
**Usuario:** bandit8
**Contraseña:** TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solucion
``` shell
ssh bandit8@bandit.labs.overthewire.org -p2220
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ cat data.txt| sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
## Notas adicionales
El sort sive para ordenar todos los archivos, con uniq buscamos la contraseña que no se repite

## Referencias
[Canalización y Redirección](https://ryanstutorials.net/linuxtutorial/piping.php)

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep