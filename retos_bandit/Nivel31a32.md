# Bandit
## Objetivo
Hay un repositorio de git en `ssh://bandit31-git@localhost/home/bandit31-git/repo`. La contraseña para el usuario `bandit31-git`es la misma que para el usuario `bandit31`.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**Usuario:** bandit31
**Contraseña:** OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solucion

``` shell
ssh bandit31@bandit.labs.overthewire.org -p2220
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

bandit31@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root root 4096 Sep  1 06:30 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rwxr-xr-x  1 root root   59 Sep  1 06:30 .gitconfig
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit31@bandit:~$ mkdir /tmp/mino23
bandit31@bandit:~$ cd /tmp/mino23

bandit31@bandit:/tmp/mino23$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo

Cloning into 'repo'...

//COLOCAMOS LO SIGUIENTE

yes
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.'

bandit31@bandit:/tmp/mino23$ cd repo
bandit31@bandit:/tmp/mino23/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 26 09:17 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 26 09:17 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 26 09:17 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 26 09:17 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 26 09:17 README.md

bandit31@bandit:/tmp/mino23/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/mino23/repo$ echo ''May I come in?'' > key.txt
bandit31@bandit:/tmp/mino23/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/mino23/repo$ git add -f key.txt
bandit31@bandit:/tmp/mino23/repo$ git commit -m key.txt
[master ee8813f] key.txt
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt

bandit31@bandit:/tmp/mino23/repo$ git push origin master

OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'

rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

```
## Notas adicionales

Para clonar en git usa el siginete comando: git clone linck del repo.
Podemos usar git log para ver los registros del git.
Con git show podemos ver registros obtenidos con git log.
Con git branch -a nos vamos a una ramificacion.
Con git reflog realiza el seguimiento de las actualizaciones en el extremo de las ramas a través de un mecanismo denominado registros de referencias o "reflogs".

## Referencias

## Comandos que puedes necesitar para resolver este nivel
git, git clonar, git log, git show, git branch -a, git reflog