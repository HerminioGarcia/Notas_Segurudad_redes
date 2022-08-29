# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** y es la única línea de texto que aparece una sola vez

## Datos de acceso
**Usuario:** bandit8
**Contraseña:** cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Solucion
ssh bandit8@bandit.labs.overthewire.org -p2220
cvX2JJa4CFALtqS87jk27qwqGhBM9plV
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ cat data.txt| sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Notas adicionales
El sort sive para ordenar todos los archivos, con uniq buscamos la contraseña que no se repite

## Referencias
[Canalización y Redirección](https://ryanstutorials.net/linuxtutorial/piping.php)

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep