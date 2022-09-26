# Bandit
## Objetivo
Hay un repositorio de git en `ssh://bandit31-git@localhost:2220/home/bandit31-git/repo`. La contraseña para el usuario `bandit31-git`es la misma que para el usuario `bandit31`.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**Usuario:** bandit31
**Contraseña:** OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solucion

``` shell
ssh bandit30@bandit.labs.overthewire.org -p2220
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

bandit30@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Sep  1 06:29 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile

bandit30@bandit:~$ mkdir /tmp/mino22
bandit30@bandit:~$ cd /tmp/mino22
bandit30@bandit:/tmp/mino22$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...

//COLOCAMOS LO SIGUIENTE

yes

xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit30-git@localhost's password:
Permission denied, please try again.
bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.

bandit30@bandit:/tmp/mino22$ cd repo

bandit30@bandit:/tmp/mino22/repo$ ls -la
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Sep 26 08:55 .
drwxrwxr-x 3 bandit30 bandit30 4096 Sep 26 08:54 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Sep 26 08:55 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Sep 26 08:55 README.md

bandit30@bandit:/tmp/mino22/repo$ cat README.md
just an epmty file... muahaha

bandit30@bandit:/tmp/mino22/repo$ git log

commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md
    
bandit30@bandit:/tmp/mino22/repo$ git show a325f29e1cc26b0f0dc5f89b4348e389b408cc87
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..029ba42
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+just an epmty file... muahaha

bandit30@bandit:/tmp/mino22/repo$ git reflog
a325f29 (HEAD -> master, origin/master, origin/HEAD) HEAD@{0}: clone: from ssh://localhost:2220/home/bandit30-git/repo

bandit30@bandit:/tmp/mino22/repo$ cd .git

bandit30@bandit:/tmp/mino22/repo/.git$ ls
branches  config  description  HEAD  hooks  index  info  logs  objects  packed-refs  refs

bandit30@bandit:/tmp/mino22/repo/.git$ cat packed-refs
# pack-refs with: peeled fully-peeled sorted
a325f29e1cc26b0f0dc5f89b4348e389b408cc87 refs/remotes/origin/master
831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret

bandit30@bandit:/tmp/mino22/repo/.git$ git show a325f29e1cc26b0f0dc5f89b4348e389b408cc87

commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..029ba42
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+just an epmty file... muahaha

bandit30@bandit:/tmp/mino22/repo/.git$ git show 831aac2e2341f009e40e46392a4f5dd318483019

OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

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
