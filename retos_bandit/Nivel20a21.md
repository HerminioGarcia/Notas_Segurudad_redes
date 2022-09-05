# Bandit
## Objetivo
Hay un binario setuid en el directorio de inicio que hace lo siguiente: establece una conexión con localhost en el puerto que especifique como argumento de la línea de comandos. Luego lee una línea de texto de la conexión y la compara con la contraseña del nivel anterior (bandit20). Si la contraseña es correcta, transmitirá la contraseña para el siguiente nivel (bandit21).

**NOTA:** intente conectarse a su propio demonio de red para ver si funciona como cree

## Datos de acceso
**Usuario:** bandit20
**Contraseña:** VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solucion
ssh bandit20@bandit.labs.overthewire.org -p2220
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15596 Sep  1 06:30 suconnect

bandit20@bandit:~$ nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &

bandit20@bandit:~$ jobs
[1]+  Running                 nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &

//Acemos la coneccion con el vinario suconnect

//nos conectamos al puerto

bandit20@bandit:~$ ./suconnect 3030
Connection received on 127.0.0.1 39878
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT

NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

## Notas adicionales
para abrir auna coneccion usamos eñ nc -lnvp y el puerto en este caso tambien mandamos la contraseña y para pasarlo a segundo plano usamos &
podemos usar jobs para ver una lista de procesos en segundo plano

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &, CTRL-Z, …)