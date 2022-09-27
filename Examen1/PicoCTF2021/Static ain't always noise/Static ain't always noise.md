# Static ain't always noise

## Objetivo 
Descripción:
¿Puedes mirar los datos en este binario: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static) ? ¡ Este [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) podría ayudar!

Sugerencias:
sin pistas

## Solución 
``` shell
//Descargamos los archivos que nos da el reto (static y ltdis.sh)

//nos dirijimos a descargas
┌──(mino20㉿kali)-[~]
└─$ cd Descargas 
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls -la
total 812
drwxr-xr-x  2 mino20 mino20   4096 sep 27 01:45 .
drwxr-xr-x 16 mino20 mino20   4096 sep 27 01:24 ..
-rw-r--r--  1 mino20 mino20  14551 sep 26 13:53 file
-rw-r--r--  1 mino20 mino20     34 sep 26 21:32 flag
-rw-r--r--  1 mino20 mino20   8376 sep 27 01:44 static
-rw-r--r--  1 mino20 mino20 776032 sep 26 12:54 strings
-rwxrwxrwx  1 mino20 mino20  10936 sep 26 22:00 warm
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ cat static  

 HH/lib64/ld-linux-x86-64.so.2GNUGNU~��������;
���= 
     Y h ""libc.so.6puts_cxa_finalizelibc_start_mainGLIBC_2.2.5_ITM_deregis � � � � � � H�H��mon_start__ITM_registerTMCloneTableu▒i       1�
 H��t��H���5�
 �%�
 @�%�
 h������%�
H�=�����^H��H���PTL��H�
 �DH�=�
 UH��
 H9�H��tH�Z
]��f.�]�@f.�H�=�
 H�5�
 UH)�H��H��H��H��?H�H��t▒H�!
 H��t
     ]��f�]�@f.��=I
 u/H�=�  UH��t
����H����!    H�=�       �
8#TT 1tt$D���o�N��UH��H�=�������]�f.�DAWAVI��AUATL�%F UH�-F SA��I��L)�H�H���W�� � @ @ �0@)▒L�p�▒V``�^y▒�                                                                             omewhere!8����������

//ejecutamso el script static
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./static
zsh: permiso denegado: ./static

//cambiamos los permisos
──(mino20㉿kali)-[~/Descargas]
└─$ chmod 777 static
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./static        
Oh hai! Wait what? A flag? Yes, it''s around here somewhere!
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./ltdis.sh 
zsh: permiso denegado: ./ltdis.sh
                                                                             
//cambiamos los permisos
┌──(mino20㉿kali)-[~/Descargas]
└─$ chmod 777 ltdis.sh 
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./ltdis.sh        
Attempting disassembly of  ...
objdump: 'a.out': No hay tal fichero
objdump: la sección '.text' se menciona en una opción -j, pero no se encuentra en ningún fichero de entrada
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ./ltdis.sh static  
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls
file  ltdis.sh  static.ltdis.strings.txt  strings
flag  static    static.ltdis.x86_64.txt   warm
                                                            
┌──(mino20㉿kali)-[~/Descargas]
└─$ cat static.ltdis.strings.txt | grep picoCTF
   1020 picoCTF{d15a5m_t34s3r_ae0b3ef2}
```

## Notas
devemos descargar los archivos que nos dan en el reto

## Referencias
[static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)
[BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh)
[Ayuda para el reto](https://medium.com/@mr-sh4n/pico-ctf-static-aint-always-noise-general-skill-aa5a35d3ff1a)
