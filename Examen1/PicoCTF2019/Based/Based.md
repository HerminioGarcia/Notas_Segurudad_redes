# Based

## Objetivo 
Descripción:
Para obtener realmente 1337, debe comprender diferentes codificaciones de datos, como hexadecimal o binario. ¿Puedes obtener la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conectar con `nc jupiter.challenges.picoctf.org 15130`.

Sugerencias:
Escuché que Python puede convertir cosas.
Puede ser útil tener varias ventanas abiertas.

## Solución 
``` shell
┌──(mino20㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
animation

//nos da unos binarios que tenemos que trasformar a texto

Please give the 01100001 01101110 01101001 01101101 01100001 01110100 01101001 01101111 01101110 as a word.
...
you have 45 seconds.....

Input:
animation

//ahora nos da un octal que tambien transformaremos a texto

Please give me the  160 151 145 as a word.
Input:
pie

//nos da un hexadecimal que transformamos en txto

Please give me the 737472656574 as a word.
Input:
street
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
```

## Notas
para entrar solo recuerda el servidor y el puerto
nc jupiter.challenges.picoctf.org 25103
tambien podemos usar erramientas externas para resolver los retos

## Referencias
[nc](https://linux.die.net/man/1/nc)
[convertidor de binario y hexadecimal](https://www.rapidtables.com/convert/number/binary-to-ascii.html)
[convertidor de octal](http://www.unit-conversion.info/texttools/octal/)