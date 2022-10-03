## fixme2
## Objetivo 
Descripción:
Solucione el error de sintaxis en el script de Python para imprimir la bandera.
[Download Python script](https://artifacts.picoctf.net/c/65/fixme2.py)

Sugerencias:
¿Son la igualdad y la asignación el mismo símbolo?

Para ver el archivo en el webshell, haga: $ nano fixme2.py

Para salir de nano, presione Ctrl y x y siga las indicaciones en pantalla.

La función str_xor no necesita ingeniería inversa para este desafío.

## Solución 
``` shell
┌──(mino20㉿kali)-[~/Descargas/fixme1]
└─$ cd ..              
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas]
└─$ cd fixme2 
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/fixme2]
└─$ python fixme2.py
  File "/home/mino20/Descargas/fixme2/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/fixme2]
└─$ nano fixme2.py

//falto un =
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) +>

  
flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/fixme2]
└─$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}

```

## Notas
Puedes usar nano para editar el archivo py

## Referencias
Sin referencia