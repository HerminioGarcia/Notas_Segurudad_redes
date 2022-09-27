# 2Warm

## Objetivo 
Descripción:
¿Puedes convertir el número 42 (base 10) a binario (base 2)?

Sugerencias:
Envíe su respuesta en el formato de bandera de nuestra competencia. Por ejemplo, si su respuesta fue '11111', enviaría 'picoCTF{11111}' como bandera.


## Solución 
``` shell
//creo que el mismo painton no lo puede hacer solo debemos poner bin

┌──(mino20㉿kali)-[~]
└─$ python
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
>>>


Bandera: picoCTF{101010}
```

## Notas
Con python podemos hacer esta convercion usando bin(base10)
que no se te olvide quitar 0b

## Referencias
Sin referencias

