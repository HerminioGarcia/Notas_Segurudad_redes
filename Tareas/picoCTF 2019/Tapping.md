# Tapping

## Objetivo 
Descripción:
Hay escuchas provenientes de los cables. ¿Qué está diciendo `nc jupiter.challenges.picoctf.org 9422`?

## Solución
Corremos el servidor
``` shell
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ nc jupiter.challenges.picoctf.org 9422  
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }
```
vemos que se trata de clave morce
usamos el CyberChef
https://gchq.github.io/CyberChef/
usamos el desifrado en clave morce
![[Pasted image 20221109141850.png]]
picoCTF{M0RS3C0D31SFUN2683824610}

## Notas
¿Qué tipo de codificación utiliza guiones y puntos?
La bandera tiene el formato PICOCTF{}

## Referencias
sin referencias.