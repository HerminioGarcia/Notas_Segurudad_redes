# rsa-pop-quiz

## Objetivo 
Descripción:
¡Clase, tomen sus asientos! Es hora PRIME para una prueba...`nc jupiter.challenges.picoctf.org 18821`

## Solución
vemos la imagen
``` shell
┌──(mino20㉿kali)-[~/Descargas]
└─$ cd The\ Numbers 
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/The Numbers]
└─$ ls
the_numbers.png
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/The Numbers]
└─$ open the_numbers.png
```
![[Pasted image 20221109092516.png]]
si consideramos el formato de la bandera podemos ver que p = 16, i =9, c=3, o=15, t=20, f=6, podemos ver que se trata de un alfabeto numerado
![[Pasted image 20221109092859.png]]

lo que podemos hacer es simplemente tradusirlo nosotros o usar la sigiente pagina

https://gchq.github.io/CyberChef/

![[Pasted image 20221109093327.png]]

usariamos la decodificasion de a1z26 y obtendriamos la bandera
solo poneos los parentecis

picoCTF{thenumbersmason}

## Notas
[información RSA](https://simple.wikipedia.org/wiki/RSA_algorithm)

## Referencias
sin referencias.