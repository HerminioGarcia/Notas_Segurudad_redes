## convertme
## Objetivo 
Descripción:
Ejecute el script de Python y convierta el número dado de decimal a binario para obtener la bandera.
[Download Python script](https://artifacts.picoctf.net/c/31/convertme.py)

Sugerencias:
¡Busque una aplicación de conversión de números decimales a binarios en la web o use la calculadora de su computadora!

La función str xor no necesita ingeniería inversa para este desafío.

Si tiene Python en su computadora, puede descargar el script normalmente y ejecutarlo. De lo contrario, use el comando wget en el webshell.

Para usar wget en el shell web, primero haga clic derecho en el enlace de descarga y seleccione 'Copiar enlace' o 'Copiar dirección de enlace'

Escriba todo después del signo de dólar en el shell web: $ wget , luego pegue el enlace después del espacio después de wget y presione enter. ¡Esto descargará el script para usted en el webshell para que pueda ejecutarlo!

Finalmente, para ejecutar el script, escriba todo después del signo de dólar y luego presione enter: $ python3 convertme.py



## Solución 
``` shell
//descargamos el archivo
//entramos a la carpeta de descargas

┌──(mino20㉿kali)-[~]
└─$ cd Descargas
                                                                   
┌──(mino20㉿kali)-[~/Descargas]
└─$ ls
Addadshashanammu      flag      static                    warm
Addadshashanammu.zip  Forence   static.ltdis.strings.txt
convertme.py          ltdis.sh  static.ltdis.x86_64.txt
file                  runme.py  strings
                                                                   
┌──(mino20㉿kali)-[~/Descargas]
└─$ python convertme.py 
If 69 is in decimal base, what is it in binary base?
Answer: yes
That isn't a binary number. Binary numbers contain only 1's and 0's'
                                                                   
┌──(mino20㉿kali)-[~/Descargas]
└─$ python convertme.py
If 99 is in decimal base, what is it in binary base?
Answer: 1100011
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}'    
```

## Notas
Para correr el programa convertme.py usamos python
recuerda que podemos usar otras pagias externas.

## Referencias
[Convertidor de datos](https://www.convertir-unidades.info/convertidor-de-unidades.php?tipo=zahlensysteme)