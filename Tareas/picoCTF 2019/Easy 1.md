# Easy 1

## Objetivo 
Descripción:
El bloc de notas de una sola vez puede ser criptográficamente seguro, pero no cuando conoce la clave. ¿Puedes resolver esto? Le proporcionamos la marca cifrada, la clave y una tabla para ayudarlo `UFJKXQZQUNB`con la clave de `SOLVECRYPTO`. ¿Puedes usar esta [tabla](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) para resolverlo?.

## Solución
vemos el archivo
``` shell
┌──(mino20㉿kali)-[~/Descargas]
└─$ cd Easy1            
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/Easy1]
└─$ ls
table.txt
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/Easy1]
└─$ open table.txt
```
vemos que es una tabla la cual es para el criptograma de tipo vigenere
mientras tengamos la llave esto sera facil de resolver
![[Pasted image 20221109100456.png]]
eto lo podemos resolver a mano pero tambien podemos usar el sigiente linck para resolver el reto
https://gchq.github.io/CyberChef/

![[Pasted image 20221109100611.png]]
solo damos el sifrado y la llave

picoCTF{CRYPTOISFUN}

## Notas
Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta fue 'hola', enviaría 'picoCTF{HOLA}' como bandera.

Utilice mayúsculas para el mensaje.

## Referencias
sin referencias.