# Bandit
## Objetivo
Hay un repositorio de git en `ssh://bandit27-git@localhost/home/bandit27-git/repo`. La contraseña para el usuario `bandit27-git` es la misma que para el usuario `bandit27`.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**Usuario:** bandit27
**Contraseña:** YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solucion

``` shell
ssh bandit27@bandit.labs.overthewire.org -p2220
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

bandit27@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Sep  1 06:29 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile

bandit27@bandit:~$ mkdir /tmp/mino20mtz

bandit27@bandit:~$ cd /tmp/mino20mtz

bandit27@bandit:/tmp/mino20mtz$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo

//COLOCAMOS LO SIGUIENTE

yes

YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.'

bandit27@bandit:/tmp/mino20mtz$ cd repo

bandit27@bandit:/tmp/mino20mtz/repo$ ls -la
total 16
drwxrwxr-x 3 bandit27 bandit27 4096 Sep 26 07:22 .
drwxrwxr-x 3 bandit27 bandit27 4096 Sep 26 07:22 ..
drwxrwxr-x 8 bandit27 bandit27 4096 Sep 26 07:22 .git
-rw-rw-r-- 1 bandit27 bandit27   68 Sep 26 07:22 README

bandit27@bandit:/tmp/mino20mtz/repo$ cat README

The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR

AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
## Notas adicionales
Para clonar en git usa el siginete comando: git clone linck del repo

## Referencias

## Comandos que puedes necesitar para resolver este nivel
git