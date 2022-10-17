# GET aHEAD

## Objetivo 
Descripción:
Encuentre la bandera que se sostiene en este servidor para adelantarse a la competencia [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

## Solución
``` shell
//nos dirigimos al enlace
//es una pagina que cambia de color
//echamos un vistaso al codigo fuete

//checamos el codigo de html y vemos que los botones que cambian el boton //son submit

<!doctype html>
<html>
<head>
<title>Red</title>
<link rel="stylesheet" type="text/css" href="[//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css](http://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css)">
<style>body {background-color: red;}</style>
</head>
<body>
<div class="container">
<div class="row">
<div class="col-md-6">
<div class="panel panel-primary" style="margin-top:50px">
<div class="panel-heading">
<h3 class="panel-title" style="color:red">Red</h3>
</div>
<div class="panel-body">
<form action="index.php" method="GET">
<input type="submit" value="Choose Red"/>
</form>
</div>
</div>
</div>
<div class="col-md-6">
<div class="panel panel-primary" style="margin-top:50px">
<div class="panel-heading">
<h3 class="panel-title" style="color:blue">Blue</h3>
</div>
<div class="panel-body">
<form action="index.php" method="POST">
<input type="submit" value="Choose Blue"/>
</form>
</div>
</div>
</div>
</div>
</div>
</body>
</html>

//vemos que los un boton resice por get y otro por post

//ahora intentaremos modificar la solisitud para que en ves de que se aga //un get se nos aga una solisitud en el get

//nos vamos al ispect y nos vamos a red

//y lansamos el get o el post 

//en las solicitudes dadas podemos itentar modificarlas

//nos dirigios a las solicitudes y demos a headers y luego resend

//se nos habre una pequeña pestaña que es para el agregar una peticion en //blanco 

//podemos cambiar el metodo de solicitud asi que ponemos head enviamos la //respuesta y si nos fijamos en la respuesta en el encabesado estara la //vandera.

picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}


//forma 2 desde la consola

┌──(mino20㉿kali)-[~]
└─$ curl -X GET http://mercury.picoctf.net:28916/index.php

<!doctype html>
<html>
<head>
    <title>Red</title>
    <link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
        <style>body {background-color: red;}</style>
</head>
        <body>
                <div class="container">
                        <div class="row">
                                <div class="col-md-6">
                                        <div class="panel panel-primary" style="margin-top:50px">
                                                <div class="panel-heading">
                                                        <h3 class="panel-title" style="color:red">Red</h3>
                                                </div>
                                                <div class="panel-body">
                                                        <form action="index.php" method="GET">
                                                                <input type="submit" value="Choose Red"/>
                                                        </form>
                                                </div>
                                        </div>
                                </div>
                                <div class="col-md-6">
                                        <div class="panel panel-primary" style="margin-top:50px">
                                                <div class="panel-heading">
                                                        <h3 class="panel-title" style="color:blue">Blue</h3>
                                                </div>
                                                <div class="panel-body">
                                                        <form action="index.php" method="POST">
                                                                <input type="submit" value="Choose Blue"/>
                                                        </form>
                                                </div>
                                        </div>
                                </div>
                        </div>
                </div>
        </body>
</html>

//con esto simulamos que estamos apretando el botón rojo

//lo intentamos con HEAD

┌──(mino20㉿kali)-[~]
└─$ curl -X HEAD http://mercury.picoctf.net:28916/index.php
Warning: Setting custom HTTP method to HEAD with -X/--request may not work the 
Warning: way you want. Consider using -I/--head instead.
                                                                                 
//lo intentamos con -I
┌──(mino20㉿kali)-[~]
└─$ curl -I HEAD http://mercury.picoctf.net:28916/index.php
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}
Content-type: text/html; charset=UTF-8


picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}
```

## Notas
Tal vez tienes más de 2 opciones

Consulte herramientas como Burpsuite para modificar sus solicitudes y ver las respuestas.

## Referencias
sin referencias