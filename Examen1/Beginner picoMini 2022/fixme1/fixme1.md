## fixme1
## Objetivo 
Descripción:
Solucione el error de sintaxis en este script de Python para imprimir la bandera.
[Download Python script](https://artifacts.picoctf.net/c/39/fixme1.py)

Sugerencias:
La sangría es muy significativa en Python

Para ver el archivo en el webshell, haga: $ nano fixme1.py

Para salir de nano, presione Ctrl y x y siga las indicaciones en pantalla.

La función str_xor no necesita ingeniería inversa para este desafío.

## Solución 
``` shell
┌──(mino20㉿kali)-[~]
└─$ cd Descargas/fixme1 
                                                                   
┌──(mino20㉿kali)-[~/Descargas/fixme1]
└─$ ls
fixme1.py
																   
//nos saldra un error de de identacion por lo que debemos editar el archivo
┌──(mino20㉿kali)-[~/Descargas/fixme1]
└─$ python fixme1.py   
  File "/home/mino20/Descargas/fixme1/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
                                                                   
┌──(mino20㉿kali)-[~/Descargas/fixme1]
└─$ nano fixme1.py

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) +>

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)

┌──(mino20㉿kali)-[~/Descargas/fixme1]
└─$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```

## Notas
Puedes usar nano para editar el archivo py

## Referencias
Sin referencia
