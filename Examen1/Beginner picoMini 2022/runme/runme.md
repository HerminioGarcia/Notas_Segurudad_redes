## runme.py

## Objetivo 
Descripción:
Ejecute el script runme.py para obtener la bandera. Descargue el script con su navegador o con wget en el shell web.
Descarga el script Python runme.py
[Download runme.py Python script](https://artifacts.picoctf.net/c/86/runme.py)

Sugerencias:
Si tiene Python en su computadora, puede descargar el script normalmente y ejecutarlo. De lo contrario, use el comando wget en el webshell.

Para usar wget en el shell web, primero haga clic derecho en el enlace de descarga y seleccione 'Copiar enlace' o 'Copiar dirección de enlace'

Escriba todo después del signo de dólar en el shell web: $ wget , luego pegue el enlace después del espacio después de wget y presione enter. ¡Esto descargará el script para usted en el webshell para que pueda ejecutarlo!

Finalmente, para ejecutar el script, escriba todo después del signo de dólar y luego presione enter: $ python3 runme.py ¡Debería tener la bandera ahora!

## Solución 
``` shell
//entramos a la carpeta de descargas

┌──(mino20㉿kali)-[~]
└─$ cd Descargas
                                                                   
┌──(mino20㉿kali)-[~/Descargas]
└─$ LS
LS: command not found
                                                                   
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls
Addadshashanammu      Forence   static.ltdis.strings.txt
Addadshashanammu.zip  ltdis.sh  static.ltdis.x86_64.txt
file                  runme.py  strings
flag                  static    warm
																

//corremos el programa runme.py
┌──(mino20㉿kali)-[~/Descargas]
└─$ python runme.py 
picoCTF{run_s4n1ty_run}
```

## Notas
Para correr el programa runme.py usamos python

## Referencias
sin referencias