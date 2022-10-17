# Scavenger Hunt

## Objetivo 
Descripción:
Hay información interesante escondida en este sitio [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/) . ¿Puedes encontrarlo?

## Solución
``` shell
//nos dirigimos a la pagina
//vemos el html
//aqui notamos este comentario

<!-- Here's the first part of the flag: picoCTF{t -->'

//seria la primera parte de la bandera

//al principio de la pagina se nos dejo una un enlase a una hoja de //estilos donde ahi estaria una parte de la bandera comentada

<link rel="stylesheet" type="text/css" href="mycss.css">
//dandole clik a mycss.css

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 '*/

//ahora nos dirigimos a javascript

<script type="application/javascript" src="myjs.js"></script>
//dandole clik a myjs.js

//nos da una pista

/* How can I keep Google from indexing my website? */

//para esto prosedemos a usar robots.txt en el buscador

http://mercury.picoctf.net:55079/robots.txt

User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

//aqui obtendremos la tercera parte

// tambien vemos una pista para el sigiente pedazo 
//Creo que este es un servidor apache... ¿puedes acceder a la siguiente //bandera?

//para poder acceder solo usamos .htaccess en el directorio

http://mercury.picoctf.net:55079/.htaccess

# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

//obtenemos la parte 4 y la pista 4

//Me encanta crear sitios web en mi Mac, puedo almacenar mucha información //allí.

//para ese almacenamiento de datos las mac usan .DS_Store asi que //intentaremos acceder desde la barra de nabegacion

http://mercury.picoctf.net:55079/.DS_Store

Congrats! You completed the scavenger hunt. Part 5: _74cceb07}

//y ya con eso tenemos la bandera

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}

```

## Notas
Debería tener suficientes pistas para encontrar los archivos, no ejecute un fuerza bruta.

¿Qué son los robots txt?

Un archivo **robots**. **txt** indica a los rastreadores de los buscadores a qué URLs de tu sitio pueden acceder. Principalmente, se utiliza para evitar que las solicitudes que recibe tu sitio lo sobrecarguen; no es un mecanismo para impedir que una página web aparezca en Google.

¿Qué es la carpeta htaccess?

El archivo . **htaccess** es un archivo de configuración básico usado por el servidor web Apache para permitirle crear reglas especiales que le indiquen a su servidor web cómo debe funcionar. Se encuentra en la **carpeta** raíz. De forma predeterminada, tu sitio de WordPress utiliza el archivo

¿Qué es .DS Store en mi Mac?

**DS_Store** archivos para almacenar opciones de visualización, como las posiciones de los iconos, **el** tamaño de la ventana del Finder y los fondos de ventana. Para eliminar **un** archivo de . **DS_Store** dañado, tendrá que usar terminal. app.

## Referencias
https://es.wikipedia.org/wiki/.DS_Store
https://developers.google.com/search/docs/advanced/robots/intro?hl=es
https://computerhoy.com/noticias/internet/que-es-htaccess-que-sirve-codigos-fundamentales-76211
