## Objetivo
La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al **puerto 30001 en localhost** usando encriptación SSL.

**Nota útil: ¿Obtienes "HEARTBEATING" y "Read R BLOCK"? Use -ign_eof y lea la sección "COMANDOS CONECTADOS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese comando...**

## Datos de acceso
**Usuario:** bandit15
**Contraseña:** jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solucion
ssh bandit15@bandit.labs.overthewire.org -p2220
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
bandit15@bandit:~$ man openssl
//para ver las caracteristicas de s_client
bandit15@bandit:~$ man s_client
bandit15@bandit:~$ openssl s_client -connect localhost:30001
//pide la contraseña del nivel anterior
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Notas adicionales
Para poder ver caracteristicas de openssl o s_client usamos el man
de ahi podemos sacar el comando que ocupamos para la conexion

## Referencias
-   [Capa de sockets seguros/Seguridad de la capa de transporte en Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
-   [Libro de recetas de OpenSSL - Pruebas con OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)

## Comandos que puedes necesitar para resolver este nivel
ssh, telnet, carolina del norte, openssl, s_client, nmap