# file-run1
## Objetivo
Se le ha proporcionado un programa, ¿qué sucede si intenta ejecutarlo en la línea de comandos?Descarga el programa [aquí](https://artifacts.picoctf.net/c/310/run) .

## Solucion
```shell
┌──(mino20㉿kali)-[~/Descargas/file-run1]
└─$ ls
'01- file-run1.md'  run
 
┌──(mino20㉿kali)-[~/Descargas/file-run1]
└─$ file run           
run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=0514683255a9ef58abe3c729e7418d07210a759e, for GNU/Linux 3.2.0, not stripped

┌──(mino20㉿kali)-[~/Descargas/file-run1]
└─$ ./run  
The flag is: picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b}   

```
picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b} 

## Notas
Para ejecutar el programa, debe hacerlo ejecutable (es decir, `$ chmod +x run`)

Intente ejecutarlo agregando un '.' delante de la ruta al archivo (es decir, `$ ./run`)

## Referencias
sin referencias.