## PW Crack 1
## Objetivo 
Descripción:
¿Puedes descifrar la contraseña para obtener la bandera?Descargue el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/18/level2.py) y también necesitará el [indicador](https://artifacts.picoctf.net/c/18/level2.flag.txt.enc) cifrado en el mismo directorio.

Sugerencias:
¿Te parece familiar esa codificación?

La `str_xor`función no necesita ingeniería inversa para este desafío.

La `str_xor`función no necesita ingeniería inversa para este desafío.

## Solución 
``` shell
//nos dirijimos a la casrpeta
┌──(mino20㉿kali)-[~]
└─$ cd Descargas/PW\ Crack\ 1 
                                                  
┌──(mino20㉿kali)-[~/Descargas/PW Crack 1]
└─$ ls
level1.flag.txt.enc  level1.py
                                                  
┌──(mino20㉿kali)-[~/Descargas/PW Crack 1]
//intentamos correr leavel1
└─$ python level1.py
Please enter correct password for flag: 
That password is incorrect
                                                   
┌──(mino20㉿kali)-[~/Descargas/PW Crack 1]
└─$ cat level1.py
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "1e1a"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

┌──(mino20㉿kali)-[~/Descargas/PW Crack 1]
└─$ nano level1.py
                                                   
//vemos que el archivo tiene el password para que nos de la bandera

┌──(mino20㉿kali)-[~/Descargas/PW Crack 1]
└─$ python level1.py
Please enter correct password for flag: 1e1a

Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}

```

## Notas
Con nano podemos ver el contenido y aparte el poder edotarlo

## Referencias
Sin referencia