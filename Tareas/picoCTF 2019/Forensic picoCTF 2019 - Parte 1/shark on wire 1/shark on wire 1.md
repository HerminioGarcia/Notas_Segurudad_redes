# shark on wire 1

## Objetivo 
Descripción:
Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap) . Recuperar la bandera.

## Solución
analizamos el archivo
``` shell
┌──(mino20㉿kali)-[~/Descargas/shark on wire 1]
└─$ ls
capture.pcap

┌──(mino20㉿kali)-[~/Descargas/shark on wire 1]
└─$ file capture.pcap                             
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
```

abrimos wireshark para capturar los paquetes
![[Pasted image 20221114015319.png]]

abrimos el archivo para capturar los paquetes
![[Pasted image 20221114015516.png]]

nos dirijimos a un protocolo UCP y podemos segir el stream de la captura de paquetes
![[Pasted image 20221114015900.png]]

![[Pasted image 20221114020123.png]]

vemos mas secuencias para ver si podemos encontrar la bandera
![[Pasted image 20221114020412.png]]

picoCTF{StaT31355_636f6e6e}

## Notas
Intenta usar una herramienta como Wireshark
¿Qué son las corrientes?

## Referencias
sin referencias.