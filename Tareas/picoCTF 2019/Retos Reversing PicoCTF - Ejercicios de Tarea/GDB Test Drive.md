# GDB Test Drive
## Objetivo
¿Puedes conseguir la bandera?Descarga este [binario](https://artifacts.picoctf.net/c/117/gdbme) .Aquí están las instrucciones de la prueba de manejo:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Solucion

```shell
┌──(mino20㉿kali)-[~/Descargas/GDBTestDrive]
└─$ ls
'01- file-run1.md'  '03- GDB Test Drive.md'  
'02- file-run2.md'   gdbme

┌──(mino20㉿kali)-[~/Descargas/GDBTestDrive]
└─$ file gdbme           
gdbme: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=3a4ddb0e34724c36111565ddb5cce3cead119973, for GNU/Linux 3.2.0, not stripped
                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/GDBTestDrive]
└─$ chmod +x gdbme
                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/GDBTestDrive]
└─$ gdb                          
GNU gdb (Debian 12.1-4) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word".
(gdb) q

┌──(mino20㉿kali)-[~/Descargas/GDBTestDrive]
└─$ gdb gdbme
GNU gdb (Debian 12.1-4) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm

```

![[Pasted image 20221129051656.png]]

picoCTF{d3bugg3r_dr1v3_7776d758}

## Notas
ninguno

## Referencias
sin referencias.