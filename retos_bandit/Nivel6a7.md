# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena **en algún lugar del servidor** y tiene todas las siguientes propiedades:

-   propiedad del usuario bandit7
-   propiedad del grupo bandit6
-   33 bytes de tamaño

## Datos de acceso
**Usuario:** bandit6
**Contraseña:** P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solucion
ssh bandit6@bandit.labs.overthewire.org -p2220
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
bandit6@bandit:~$ ls
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c
//se nos cargan varios arcivos se sospecha del .password
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Notas adicionales
Con el comando find podemos buscar por tamaño del archivo, nombre, decha de creacion, por permisos, etc.
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
en este caso lo buscamos por usuario, grupo y tamaño y con lo otro nos muestra los archivos a los que tenemos acceso.

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep