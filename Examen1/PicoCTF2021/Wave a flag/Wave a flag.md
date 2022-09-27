# Wave a flag

## Objetivo 
Descripción:
¿Puede invocar banderas de ayuda para una herramienta o binario? [Este programa](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) tiene información extraordinariamente útil...

Sugerencias:
Este programa solo funcionará en webshell u otra computadora con Linux.

Para acceder al archivo en su shell, ingrese lo siguiente en el indicador de Terminal:`$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm`

Ejecute este programa ingresando lo siguiente en el indicador de Terminal: `$ ./warm`, pero primero tendrá que hacerlo ejecutable con`$ chmod +x warm`

-h y --help son los argumentos más comunes que se dan a los programas para obtener más información de ellos.

No todos los programas implementan funciones de ayuda como -h y --help.

## Solución 
``` shell
//nos dirijimos a descargas
┌──(mino20㉿kali)-[~]
└─$ cd Descargas
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./warm      
zsh: permiso denegado: ./warm
                                                                         // vemos los permisos de warm    
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls -la
total 800
drwxr-xr-x  2 mino20 mino20   4096 sep 26 22:00 .
drwxr-xr-x 16 mino20 mino20   4096 sep 26 21:39 ..
-rw-r--r--  1 mino20 mino20  14551 sep 26 13:53 file
-rw-r--r--  1 mino20 mino20     34 sep 26 21:32 flag
-rw-r--r--  1 mino20 mino20 776032 sep 26 12:54 strings
-rw-r--r--  1 mino20 mino20  10936 sep 26 22:00 warm
                                                                         // damos los permisos de warm     
┌──(mino20㉿kali)-[~/Descargas]
└─$ chmod 777 warm                                        
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls -la        
total 800
drwxr-xr-x  2 mino20 mino20   4096 sep 26 22:00 .
drwxr-xr-x 16 mino20 mino20   4096 sep 26 21:39 ..
-rw-r--r--  1 mino20 mino20  14551 sep 26 13:53 file
-rw-r--r--  1 mino20 mino20     34 sep 26 21:32 flag
-rw-r--r--  1 mino20 mino20 776032 sep 26 12:54 strings
-rwxrwxrwx  1 mino20 mino20  10936 sep 26 22:00 warm
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./warm             
Hello user! Pass me a -h to learn what I can do!
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}

picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```

## Notas
fijate en los permisos, aveces solo vasta con tener los permisos para pasar de nivel.

## Referencias
 [linck del programa](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm)