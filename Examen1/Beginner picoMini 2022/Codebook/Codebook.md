## Codebook
## Objetivo 
Descripción:
Ejecute el script de Python code.py en el mismo directorio que codebook.txt.
-   [Download code.py](https://artifacts.picoctf.net/c/102/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/102/codebook.txt)


Sugerencias:
En el shell web, use ls para ver si ambos archivos están en el directorio en el que se encuentra

La función str_xor no necesita ingeniería inversa para este desafío.

## Solución 
``` shell
//descargamos el archivo
//y los metemos a una carpeta
//nos dirijimos a la carpeta que creamso

┌──(mino20㉿kali)-[~]
└─$ cd Descargas/Codebook 
                                                                   
┌──(mino20㉿kali)-[~/Descargas/Codebook]
└─$ ls
codebook.txt  code.py
                                                   
┌──(mino20㉿kali)-[~/Descargas/Codebook]
└─$ cat codebook.txt 
azbycxdwevfugthsirjqkplomn
                                                   
┌──(mino20㉿kali)-[~/Descargas/Codebook]
└─$ python code.py        
picoCTF{c0d3b00k_455157_197a982c}    
```

## Notas
Para correr el programa code.py usamos python
recuerda qe podemos usar otras pagias externas.

## Referencias
Sin referencia