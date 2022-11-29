# patchme.py
## Objetivo
¿Puedes conseguir la bandera?Ejecute este [programa de Python](https://artifacts.picoctf.net/c/388/patchme.flag.py) en el mismo directorio que esta [bandera cifrada](https://artifacts.picoctf.net/c/388/flag.txt.enc) .

## Solucion

```shell
┌──(mino20㉿kali)-[~/Descargas/patchme]
└─$ ls
'01- file-run1.md'  '03- GDB Test Drive.md'   Help-pictures-notes
'02- file-run2.md'  '04- patchme.py.md'    flag.txt.enc       patchme.flag.py

┌──(mino20㉿kali)-[~/Descargas/patchme]
└─$ file patchme.flag.py
patchme.flag.py: ASCII text, with CRLF line terminators

┌──(mino20㉿kali)-[~/Descargas/patchme]
└─$ file flag.txt.enc   
flag.txt.enc: data

┌──(mino20㉿kali)-[~/Descargas/patchme]
└─$ cat patchme.flag.py
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


flag_enc = open('flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "ak98" + \
                   "-=90" + \
                   "adfjhgj321" + \
                   "sleuth9000"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), "utilitarian")
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

┌──(mino20㉿kali)-[~/Descargas/patchme]
└─$ cat flag.txt.enc

CR1@    UYX+
6FP_S
     FG 

┌──(mino20㉿kali)-[~/Descargas/patchme]
└─$ python  patchme.flag.py
Please enter correct password for flag: ak98-=90adfjhgj321sleuth9000
Welcome back... your flag, user:
picoCTF{p47ch1ng_l1f3_h4ck_21d62e33}
```

## Notas
ninguno

## Referencias
sin referencias.