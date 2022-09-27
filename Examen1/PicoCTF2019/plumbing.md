# plumbing

## Objetivo 
A veces necesita manejar datos de proceso fuera de un archivo. ¿Puedes encontrar una manera de mantener la salida de este programa y buscar la bandera? Conectar a `jupiter.challenges.picoctf.org 14291`.

Sugerencias:
Recuerda que el formato de la bandera es picoCTF{XXXX}
¿Qué es una pipa? No, no ese tipo de pipa... Este [tipo](http://www.linfo.org/pipes.html)

## Solución 
``` shell
//Es posible combinar dos comandos para que nos de directamente la bandera solo agregamos el grep picoCTF.
┌──(mino20㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 14291 | grep picoCTF
picoCTF{digital_plumb3r_ea8bfec7}
```

## Notas
Recuerda que podemos agregar el grep para facilitar la busqueda de la bandera

## Referencias
[nc](https://linux.die.net/man/1/nc)
[convertidor de binario y hexadecimal](https://www.rapidtables.com/convert/number/binary-to-ascii.html)
[convertidor de octal](http://www.unit-conversion.info/texttools/octal/)