# unpackme.py
## Objetivo
¿Puedes conseguir la bandera?Ingeniería inversa de este [programa de Python](https://artifacts.picoctf.net/c/466/unpackme.flag.py) .

## Soluciòn
```shell
┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ ls
'01- file-run1.md'  '03- GDB Test Drive.md'  '05- Safe Opener.md'    unpackme.flag.py
'02- file-run2.md'  '04- patchme.py.md'      '06- unpackme.py.md'   Help-pictures-notes

┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ file unpackme.flag.py
unpackme.flag.py: Python script, ASCII text executable, with very long lines (305)

┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ cat unpackme.flag.py
import base64
from cryptography.fernet import Fernet



payload = b'gAAAAABiMD09KmaS5E6AQNpRx1_qoXOBFpSny3kyhr8Dk_IEUu61Iu0TaSIf8RCyf1LJhKUFVKmOt2hfZzynRbZ_fSYYN_OLHTTIRZOJ6tedEaK6UlMSkYJhRjAU4PfeETD-8gDOA6DQ8eZrr47HJC-kbyi3Q5o3Ba28mutKCAkwrqt3gYOY9wp3dWYSWzP4Tc3NOYWfu-SJbW997AM8GA-APpGfFrf9f7h0VYcdKOKu4Vq9zjJwmTG2VXWFET-pkF5IxV3ZKhz36L5IvZy1dVZXqaMR96lovw=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
exec(plain.decode())

┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ python unpackme.flag.py
What''s the password? 1
That password is incorrect.

┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ nano unpackme.flag.py

┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ cat unpackme.flag.py   
import base64
from cryptography.fernet import Fernet



payload = b'gAAAAABiMD09KmaS5E6AQNpRx1_qoXOBFpSny3kyhr8Dk_IEUu61Iu0TaSIf8RCyf1LJhKUFVKmOt2hfZzynRbZ_fSYYN_OLHTTIRZOJ6tedEaK6UlMSkYJhRjAU4PfeETD-8gDOA6DQ8eZrr47HJC-kbyi3Q5o3Ba28mutKCAkwrqt3gYOY9wp3dWYSWzP4Tc3NOYWfu-SJbW997AM8GA-APpGfFrf9f7h0VYcdKOKu4Vq9zjJwmTG2VXWFET-pkF5IxV3ZKhz36L5IvZy1dVZXqaMR96lovw=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
print(plain.decode())
exec(plain.decode())

┌──(mino20㉿kali)-[~/Descargas/unpackme]
└─$ python unpackme.flag.py

pw = input('What\'s the password? ')

if pw == 'batteryhorse':
  print('picoCTF{175_chr157m45_85f5d0ac}')
else:
  print('That password is incorrect.')


What''s the password? 1
That password is incorrect.
```
picoCTF{175_chr157m45_85f5d0ac}

## Notas
ninguno

## Referencias
sin referencias.