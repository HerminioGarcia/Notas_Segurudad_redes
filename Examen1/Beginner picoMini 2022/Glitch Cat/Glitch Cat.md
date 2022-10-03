## Glitch Cat
## Objetivo 
Descripción:
¡Nuestro servicio de impresión de banderas ha comenzado a fallar!`$ nc saturn.picoctf.net 51109`

Sugerencias:
ASCII es una de las codificaciones más comunes utilizadas en la programación

¡Sabemos que la salida de falla es Python válida, de alguna manera!

Presione Ctrl y c en su teclado para cerrar su conexión y regresar al símbolo del sistema.

## Solución 
``` shell
//entramos al servidor
┌──(mino20㉿kali)-[~]
└─$ nc saturn.picoctf.net 51109  
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
                                                                                                                                                                       
//podemos usar python para desifrar la bandera
┌──(mino20㉿kali)-[~]
└─$ python          
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
'picoCTF{gl17ch_m3_n07_bda68f75}'

```

## Notas
Python te puede ayedar con codigo ASCII

## Referencias
Sin referencia