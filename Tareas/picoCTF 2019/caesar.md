# caesar

## Objetivo 
Descripción:
Descifrar este [mensaje](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext) .

## Solución
vemos la imagen
``` shell
┌──(mino20㉿kali)-[~/Descargas]
└─$ cd caesar 
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ ls
ciphertext
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ cat ciphertext     
picoCTF{ynkooejcpdanqxeykjrbdofgkq}
```
para este reto iremos a CyberChef y de aqui usaremos rot13 para intentar encontrar la vandera
https://gchq.github.io/CyberChef/

![[Pasted image 20221109123125.png]]

vamos incrementando de uno en uno para encotrar la vandera.

picoCTF{crossingtherubiconvfhsjkou}

## Notas
[tutorial](https://learncryptography.com/classical-encryption/caesar-cipher) de cifrado césar

## Referencias
sin referencias.