# Bandit
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** junto a la palabra **millonésima** en ingles **millionth**

## Datos de acceso
**Usuario:** bandit7
**Contraseña:** HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Solucion
ssh bandit7@bandit.labs.overthewire.org -p2220
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ cat data.txt | grep millionth
//salen muchas contraseñas podemos buscarlas usando  | grep millionth
// para que busque de una mejor manera
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV

OTRA FORMA

bandit7@bandit:~$ grep millionth data.txt
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Notas adicionales
Con el comando grep creamos un filtro a la hora de revisar el archivo con cat

## Referencias

## Comandos que puedes necesitar para resolver este nivel
ls , cd, cat, file, du, find , grep