# Lets Warm Up 

## Objetivo 
Descripción:
Si te dijera que una palabra comienza con 0x70 en hexadecimal, ¿con qué comenzaría en ASCII?

Sugerencias
Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta fue "hola", enviaría "picoCTF{hola}" como bandera.


## Solución 
``` shell
//Usando echo -e podemos convertir el hexadecimal que nos dan a código ASCII

┌──(mino20㉿kali)-[~]
└─$ echo -e "\0x70"
p
                                                                             
┌──(mino20㉿kali)-[~]
└─$


Bandera: picoCTF{p}
```

## Referencias
https://cybercrack.net/write-ups/picoctf-2019/general-skills-picoctf-2019/lets-warm-up/