# Magikarp Ground Mission

## Objetivo 
Descripción:
¿Sabes cómo moverte entre directorios y leer archivos en el shell? Inicie el contenedor, `ssh` y luego `ls` una vez conectado para comenzar. Inicie sesión a través de `ssh` como `ctf-player` con la contraseña, `6dee9772`

Sugerencias:
¡Encontrar una hoja de trucos para bash sería realmente útil!

## Solución 
``` shell
//entramos al servidor ssh 
//ssh ctf-player@venus.picoctf.net -p 57736

┌──(mino20㉿kali)-[~]
└─$ ssh ctf-player@venus.picoctf.net -p 57736

//colocamos la contraseña: 6dee9772
//sesupone que devemos obtener la bandera pero por partes
//vemos el ls para intentar consegir la primera parte

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt

//aqui solo usamos un cat en el 1of3.flag.txt 

ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_

//nos movemos al sigiente archivo para obtener la segunda //parte

ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`

// nos movemos al cd /

ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  dev   instructions-to-3of3.txt  media  proc  sbin  tmp
bin            etc   lib                       mnt    root  srv   usr
boot           home  lib64                     opt    run   sys   var

//usamos cat en 2of3.flag.txt para la segunda parte

ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_

//para obtener la tercera parte usamos el cat instructions-to-3of3.txt

ctf-player@pico-chall$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`

//nos movemos a cd ~

ctf-player@pico-chall$ cd ~

ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in

//obtenemos la tercera parte con el cat 3of3.flag.txt

ctf-player@pico-chall$ cat 3of3.flag.txt
540e4e79}
```

## Notas
Conecta al server del ssh con el siguiente comando
ssh ctf-player@venus.picoctf.net -p 57736

## Referencias
sin referencias