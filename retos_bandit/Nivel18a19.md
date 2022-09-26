# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo **Léame** en el directorio de inicio. Desafortunadamente, alguien ha modificado **.bashrc** para cerrar la sesión cuando inicia sesión con SSH.

## Datos de acceso
**Usuario:** bandit18
**Contraseña:** hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solucion
``` shell
ssh bandit18@bandit.labs.overthewire.org -p2220 cat readme
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

ssh bandit18@bandit.labs.overthewire.org -p2220 cat readme /bin/bash
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

ssh bandit18@bandit.labs.overthewire.org -p2220 "/bin/bash"
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

ls
readme
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```
## Notas adicionales
podemos ver los archivos antes de conectarnos poniendo de lado el comando (en este caso lo manejamos asi porque este juego nos sacaba cada que ingresabamos)

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ssh, ls, cat