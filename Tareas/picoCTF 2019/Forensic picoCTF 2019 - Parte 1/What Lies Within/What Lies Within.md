# What Lies Within

## Objetivo 
Descripción:
Hay algo en el [edificio](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png) . ¿Puedes recuperar la bandera?

## Solución
vemos que usa la tecnica de steganography
que es para ocultar informacion en un archivo no escondida
``` shell
┌──(mino20㉿kali)-[~/Descargas/What Lies Within]
└─$ ls
buildings.png
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/What Lies Within]
└─$ open buildings.png
```

podemos decodificar la imagen en el siguiente linck
https://stylesuxx.github.io/steganography/

![[Pasted image 20221114025102.png]]

## Notas
Hay datos codificados en alguna parte... podría haber un decodificador en línea.

## Referencias
[decodificador](https://stylesuxx.github.io/steganography/)