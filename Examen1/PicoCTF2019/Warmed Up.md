# Warmed Up

## Objetivo 
Descripción:
¿Qué es 0x3D (base 16) en decimal (base 10)?

Sugerencias:
Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta fue '22', enviaría 'picoCTF{22}' como bandera.


## Solución 
``` shell
//Estamos buscando una conversión hexadecimal a decimal de "3D" a decimal. Ahi que tenga en cuenta que 0x significa que el valor es un valor hexadecimal y no se tiene en cuenta en ningún cálculo.

//abrimos el python y colocamos 0x3D
┌──(mino20㉿kali)-[~]
└─$ python                
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x3D
61
>>>


Bandera: picoCTF{61}
```

## Notas
El sistema hexadecimal es una técnica de numeración que tiene como base el 16. Se trata de un esquema alternativo al sistema decimal y al binario

El sistema hexadecimal es aquel que utiliza entonces dieciséis dígitos, que serán los siguientes:

0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F

En dicho conjunto, las letras del alfabeto latino tienen el siguiente valor expresado en el sistema decimal:

A=10, B=11, C=12, D=13, E=14 y F=15

## Referencias
https://economipedia.com/definiciones/sistema-hexadecimal.html#:~:text=El%20sistema%20hexadecimal%20es%20una,sistema%20decimal%20y%20al%20binario.

https://cybercrack.net/write-ups/picoctf-2019/general-skills-picoctf-2019/warmed-up/

