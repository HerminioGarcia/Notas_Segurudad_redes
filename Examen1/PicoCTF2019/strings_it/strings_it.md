# strings it

## Objetivo 
Descripción:
¿Puedes encontrar el indicador en el  [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) sin ejecutarlo?

Sugerencias:
[strings](https://linux.die.net/man/1/strings)


## Solución 
``` shell
┌──(mino20㉿kali)-[~]
└─$ ls
Descargas   Escritorio  Música      Público
Documentos  Imágenes    Plantillas  Vídeos
                                                                             
┌──(mino20㉿kali)-[~]
└─$ cd Descargas 
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls
strings
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_d66c7bb7}

```

## Notas
No olvides ir a la carpeta de descargas

## Referencias
[strings](https://linux.die.net/man/1/strings)