# First Grep

## Objetivo 
Descripción:
¿Puedes encontrar la bandera en el  [file](https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file)? Esto sería muy tedioso de revisar manualmente, algo me dice que hay una mejor manera.

Sugerencias:
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución 
//Descargamos el file y nos vamos a descargas
``` shell
┌──(mino20㉿kali)-[~]
└─$ cd Descargas 
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ grep 'picoCTF' file
picoCTF{grep_is_good_to_find_things_f77e0797}
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$
```

## Notas
usamos grep para viscar picoCTF en file

## Referencias
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)