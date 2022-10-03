## PW Crack 2

## Objetivo 
Descripción:
¿Puedes descifrar la contraseña para obtener la bandera?
Descargue el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/18/level2.py) y también necesitará el [indicador](https://artifacts.picoctf.net/c/18/level2.flag.txt.enc)cifrado en el mismo directorio.

Sugerencias:
¿Te parece familiar esa codificación?

La `str_xor` función no necesita ingeniería inversa para este desafío.

## Solución 
``` shell
//nos dirijimos a donde tengo los archivos
┌──(mino20㉿kali)-[~]
└─$ cd Descargas/PW\ Crack\ 2
                                                  
┌──(mino20㉿kali)-[~/Descargas/PW Crack 2]
└─$ ls
level2.flag.txt.enc  level2.py
                                                  
//vemos el .py
┌──(mino20㉿kali)-[~/Descargas/PW Crack 2]
└─$ python level2.py 
Please enter correct password for flag: 
That password is incorrect
                                                  
//vemos el level2.flag.txt.enc 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 2]
└─$ cat level2.flag.txt.enc  
CP
pm%GKWP[fVT]^R
              TfVU\Q\                                                  
//hacemos un cat a level2.py para ver si tenemos la contraseña 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 2]
└─$ cat level2.py          
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
                                                  
//vemos que si esta esa contraseña pero esta en caracteres ASCII
//asi que en el mismo archivo de python ponemos un print para que nos
//muestre esta contraseña
┌──(mino20㉿kali)-[~/Descargas/PW Crack 2]
└─$ nano level2.py 
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/PW Crack 2]
└─$ python level2.py       
39ce
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}

```

## Notas
Con nano podemos ver el contenido y aparte el poder edotarlo

## Referencias
Sin referencia