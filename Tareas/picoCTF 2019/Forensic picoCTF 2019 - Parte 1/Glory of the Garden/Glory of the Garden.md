# Glory of the Garden

## Objetivo 
Descripción:
Este [jardín](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contiene más de lo que parece.

## Solución
vemos la imagen y usamos el hexeditor
``` shell
┌──(mino20㉿kali)-[~/Descargas/Glory of the Garden]
└─$ ls                                            
garden.jpg
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/Glory of the Garden]
└─$ open garden.jpg 
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/Glory of the Garden]
└─$ hexeditor garden.jpg
```
![[Pasted image 20221114010942.png]]

oprimimos ctrl+w y hacemos la busqueda en mostramos en texto
![[Pasted image 20221114011201.png]]

podemos buscar la bandera poniendo despues picoCTF
![[Pasted image 20221114011446.png]]

aqui estaria la vandera
![[Pasted image 20221114011613.png]]

tambien podriamos usar strings para ver los textos y filtrar la bandera
``` shell
┌──(mino20㉿kali)-[~/Descargas/Glory of the Garden]
└─$ strings garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
```

## Notas
¿Qué es un editor hexadecimal?

## Referencias
sin referencias.