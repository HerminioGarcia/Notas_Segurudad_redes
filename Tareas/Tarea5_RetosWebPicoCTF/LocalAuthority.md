# Local Authority
## Objetivo
¿Puedes conseguir la bandera?Vaya a este [sitio web](http://saturn.picoctf.net:55826/) y vea lo que puede descubrir.

## Soluciòn
Entramos a la pagina y lo primero a notar es el login.
![[Pasted image 20221028171309.png]]
intentamos logearnos con cualquier usuario,
![[Pasted image 20221028172050.png]]
despues estando en log in failed abriremos el inspector y nos dirigimos a Network.
vemos tres status uno con metodo post y dos con metodo get.
lo que nos interesa aqui es revisar los archivos login.php y secure.js para verlos solo hacemos clik en ellos.
![[Pasted image 20221028172207.png]]


Si ententamos entrar con cualquier usuario y una contraseña random podemos ver que, al inspecionar la pàgina, en la parte de Network vemos dos dominos con los archvos *login.php* y *secure.js* , podemos analizar a ambos archivos dando click derecho y en abrir en nueva pestaña, nos abrirà una nueva penstaña. 

![[Screenshot_2022-10-14_12_21_45 1.png]]

El archivo *secure.js* nos muestra un còdigo.

![[Screenshot_2022-10-14_12_23_54.png]]

El còdigo es el siguiente, el cual nos da el usuario y la contraseña, ingresamos ambos datos a la pàgina de inicio para logearnos.
```shell
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

![[Screenshot_2022-10-14_12_33_21.png]]

Y al acceder nos dan inmediatamente la flag de este reto.

![[Screenshot_2022-10-14_12_34_14.png]]

picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}

## Notas
¿Cómo se comprueba la contraseña en este sitio web?

## Referencias
Sin referencia