# Tab, Tab, Attack

## Objetivo 
Descripción:
El uso de tabcomplete en la Terminal agregará años a su vida, especialmente. cuando se trata de estructuras de directorios y nombres de archivos largos e inconexos: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

Sugerencias:
Después de 'descomprimir', este problema se puede resolver presionando 11 botones... (principalmente Tabulador)...

## Solución 
``` shell
//Descargamos Addadshashanammu.zip

//Nos dirijimos a descargas
┌──(mino20㉿kali)-[~]
└─$ cd Descargas
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls
Addadshashanammu.zip  ltdis.sh                  static.ltdis.x86_64.txt
file                  static                    strings
flag                  static.ltdis.strings.txt  warm
                                                                             
//descomprimimos el zip
┌──(mino20㉿kali)-[~/Descargas]
└─$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
                                                                             
//nos dirigimos al final de las carpetas que nos dio el zip
//masomenos apretamos 7 veces el tabulador
┌──(mino20㉿kali)-[~/Descargas]
└─$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku 
                                                                             
┌──(mino20㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet
                                                                             
//podemos ver con el comando file las caracteristicas de //fang-of-haynekhtnamet donde notamos que es un archivo //ejecutable ELF de 64 bits asi que lo ejecutamos con ./

┌──(mino20㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=47e898db922f38cb54ab4a08fb4e3def5a1cb6a1, not stripped
                                                                             
┌──(mino20㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet 
ZAP! picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
```

## Notas
Podemos usar grep para obtener la contraseña o abrir el archivo de manera manual

## Referencias
 [Descargar bandera](https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag)