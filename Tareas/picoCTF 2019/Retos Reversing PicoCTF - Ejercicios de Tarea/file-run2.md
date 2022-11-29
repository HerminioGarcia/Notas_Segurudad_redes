# file-run2
## Objetivo
Otro programa, pero esta vez, parece querer algo de entrada. ¿Qué sucede si intenta ejecutarlo en la línea de comando con la entrada "¡Hola!"?Descarga el programa [aquí](https://artifacts.picoctf.net/c/353/run) .

## Solucion
```shell
┌──(mino20㉿kali)-[~/Descargas/file-run2]
└─$ ls
'01- file-run1.md'  '02- file-run2.md'  run

┌──(mino20㉿kali)-[~/Descargas/file-run2]
└─$ file run
run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=e923d195967f2f793c6de52cee78b8fb7f3c0a2a, for GNU/Linux 3.2.0, not stripped
  
┌──(mino20㉿kali)-[~/Descargas/file-run2]
└─$ ./run Hello!
The flag is: picoCTF{F1r57_4rgum3n7_f65ed63e}   
```
picoCTF{F1r57_4rgum3n7_f65ed63e} 

## Notas
Intente ejecutarlo y agregue la frase "¡Hola!" con un espacio al frente (es decir, "./run Hello!")

## Referencias
sin referencias.