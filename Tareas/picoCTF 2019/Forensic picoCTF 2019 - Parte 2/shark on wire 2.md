# shark on wire 2

## Objetivo
Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap) . Recupera la bandera que fue sustraída de la red.

## Solucion
Usamos wireshark para analizar el documento que descaramos, en mi caso lo tuve que renombrar, originalmente se llamaba capture.pcap, y como ya tenia un documento que se llama de la misma forma que se usò en un reto similar a este, lo renombre a capture2.pcap.

Parapoder analizar, teneos que abrirlo desde el programa Wireshark, el cual ya habìamos usado en un reto anterior.

![[Pasted image 20221115052626.png]]

![[Pasted image 20221115052654.png]]

nos dirigimos a un protocolo UDP

![[Pasted image 20221115052834.png]]

En la parte  de `User Datagram Protocol` damos click derecho, luego a `Follow` y a `UDP Stream`,  se abrirà una ventana e iremos modifiando los numeros de la parte de Stream, pero es un poco tardado.
![[Pasted image 20221115053017.png]]
Asi que usaremos un programa en python para poder sacar la flag mas rapidamente.

```shell
┌──(mino20㉿kali)-[~/Descargas/shark on wire 2]
└─$ nano shark2.py  
```
En el archivo, desde nano, ponemos lo sigiente

![[Pasted image 20221115053636.png]]

```shell
┌──(mino20㉿kali)-[~/Descargas/shark on wire 2]
└─$ python shark2.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
picoCTF{p1LLf3r3d_data_v1a_st3g0}

## Notas
(Ninguna)

## Referencias