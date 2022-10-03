## PW Crack 3

## Objetivo 
Descripción:
¿Puedes descifrar la contraseña para obtener la bandera?Descargue el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/23/level3.py) y también necesitará el [indicador](https://artifacts.picoctf.net/c/23/level3.flag.txt.enc) cifrado y el [hash](https://artifacts.picoctf.net/c/23/level3.hash.bin) en el mismo directorio.Hay 7 contraseñas potenciales con 1 siendo correcta. Puede encontrarlos examinando el script del verificador de contraseñas.

Sugerencias:
Para ver el archivo level3.hash.bin en webshell, haga lo siguiente:`$ bvi level3.hash.bin`

Para salir `bvi`escriba `:q`y presione enter.

La `str_xor`función no necesita ingeniería inversa para este desafío.

## Solución 
``` shell
//nos dirijimos a donde tengo los archivos
┌──(mino20㉿kali)-[~]
└─$ cd Descargas/PW\ Crack\ 3
                                                                                 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ ls
level3.flag.txt.enc  level3.hash.bin  level3.py
                                                                                 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ python level3.py
Please enter correct password for flag: 
That password is incorrect
                                                                                 
//modifique el py para ver las listas de las contraseñas y probarlas
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ nano level3.py
                                                                                 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ python level3.py
6997 3ac8 f0ac 4b17 ec27 4e66 865e
Please enter correct password for flag: 6997
That password is incorrect
                                                                                 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ python level3.py
6997 3ac8 f0ac 4b17 ec27 4e66 865e
Please enter correct password for flag: 3ac8
That password is incorrect
                                                                                 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ python level3.py
6997 3ac8 f0ac 4b17 ec27 4e66 865e
Please enter correct password for flag: f0ac
That password is incorrect
                                                                                 
┌──(mino20㉿kali)-[~/Descargas/PW Crack 3]
└─$ python level3.py
6997 3ac8 f0ac 4b17 ec27 4e66 865e
Please enter correct password for flag: 4b17
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}

```

## Notas
Con nano podemos ver el contenido y aparte el poder edotarlo

## Referencias
Sin referencia