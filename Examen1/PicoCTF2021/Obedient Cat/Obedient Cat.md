# Obedient Cat

## Objetivo 
Descripción:
Este archivo tiene una bandera a plena vista (aka "in-the-clear"). [Descargar bandera](https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag).

Sugerencias:
Cualquier sugerencia sobre cómo ingresar un comando en la Terminal (como la siguiente), comenzará con un '$'... todo lo que esté después del signo de dólar se escribirá (o copiará y pegará) en su Terminal.

  
Para acceder al archivo en su shell, ingrese lo siguiente en el indicador de Terminal: $ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag

$ man cat

## Solución 
``` shell
//que no se te olvide ir a descargas
┌──(mino20㉿kali)-[~]
└─$ cd Descargas 
                                                                             
┌──(mino20㉿kali)-[~/Descargas]
└─$ grep 'picoCTF' flag
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
```

## Notas
Podemos usar grep para obtener la contraseña o abrir el archivo de manera manual

## Referencias
 [Descargar bandera](https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag)