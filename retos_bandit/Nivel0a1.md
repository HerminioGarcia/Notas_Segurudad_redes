# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **Léame** ubicado en el directorio de inicio. Use esta contraseña para iniciar sesión en bandit1 usando SSH. Siempre que encuentre una contraseña para un nivel, use SSH (en el puerto 2220) para iniciar sesión en ese nivel y continuar el juego.

## Datos de acceso
**Usuario:** bandit0
**Contraseña:** bandit0

## Solucion
ssh bandit0@bandit.labs.overthewire.org -p2220
bandit0
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$

## Notas adicionales
## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep
