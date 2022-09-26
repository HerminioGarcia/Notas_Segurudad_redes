# Bandit
## Objetivo
La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al **puerto 30000 en localhost** .

## Datos de acceso
**Usuario:** bandit14
**Contraseña:** fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solucion
``` shell
ssh bandit14@bandit.labs.overthewire.org -p2220
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## Notas adicionales
nc host puerto se conecta a un host en un puerto determinado

## Referencias
-   [Cómo funciona Internet en 5 minutos (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) (No es del todo exacto, pero lo suficientemente bueno para principiantes)
-   [Direcciones IP](http://computer.howstuffworks.com/web-server5.htm)
-   [Dirección IP en Wikipedia](https://en.wikipedia.org/wiki/IP_address)
-   [Servidor local en Wikipedia](https://en.wikipedia.org/wiki/Localhost)
-   [Puertos](http://computer.howstuffworks.com/web-server8.htm)
-   [Puerto (redes de computadoras) en Wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))

## Comandos que puedes necesitar para resolver este nivel
ssh, telnet, nc, openssl, s_client, nmap