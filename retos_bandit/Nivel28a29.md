# Bandit
## Objetivo
Hay un repositorio de git en  `ssh://bandit28-git@localhost:2220/home/bandit28-git/repo`.  La contraseña para el usuario `bandit28-git`es la misma que para el usuario `bandit28`.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**Usuario:** bandit28
**Contraseña:** AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solucion

``` shell
ssh bandit28@bandit.labs.overthewire.org -p2220
AVanL161y9rsbcJIsFHuw35rjaOM19nR

bandit28@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Sep  1 06:29 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile

bandit28@bandit:~$ mkdir /tmp/mino20Mtz

bandit28@bandit:~$ cd /tmp/mino20Mtz

bandit28@bandit:/tmp/mino20Mtz$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo

//COLOCAMOS LO SIGUIENTE

yes

AVanL161y9rsbcJIsFHuw35rjaOM19nR

bandit28-git@localhost's password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), 798 bytes | 798.00 KiB/s, done.
Resolving deltas: 100% (2/2), done.'

bandit28@bandit:/tmp/mino20Mtz$ cd repo

bandit28@bandit:/tmp/mino20Mtz/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Sep 26 07:54 .
drwxrwxr-x 3 bandit28 bandit28 4096 Sep 26 07:53 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Sep 26 07:54 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Sep 26 07:54 README.md

bandit28@bandit:/tmp/mino20Mtz/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/mino20Mtz/repo$ git log

commit 43032edb2fb868dea2ceda9cb3882b2c336c09ec (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    fix info leak

commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

commit 43d032b360b700e881e490fbbd2eee9eccd7919e
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:24 2022 +0000

    initial commit of README.md

bandit28@bandit:/tmp/mino20Mtz/repo$ git show 43032edb2fb868dea2ceda9cb3882b2c336c09ec
commit 43032edb2fb868dea2ceda9cb3882b2c336c09ec (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx

bandit28@bandit:/tmp/mino20Mtz/repo$ git show bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: <TBD>
+- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
## Notas adicionales
Para clonar en git usa el siginete comando: git clone linck del repo.
Podemos usar git log para ver los registros del git.
Con git show podemos ver registros obtenidos con git log.

## Referencias

## Comandos que puedes necesitar para resolver este nivel
git