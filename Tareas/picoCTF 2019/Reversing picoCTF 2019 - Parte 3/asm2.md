# asm2
## Objetivo
¿Qué devuelve asm2(0x4,0x2d)? Envíe la bandera como un valor hexadecimal (comenzando con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/ceac75672637589213b952abe32c84b3/test.S)

## Solucion
descargamos el archivo
```shell
┌──(mino20㉿kali)-[~/Descargas/asm2]
└─$ ls -la
total 36
drwxr-xr-x 2 mino20 mino20  4096 nov 29 00:42 .
drwxr-xr-x 5 mino20 mino20 28672 nov 29 00:42 ..
-rw-r--r-- 1 mino20 mino20   478 nov 29 00:42 test.S
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm2]
└─$ cat test.S 
asm2:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x50c <asm2+31>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  add    DWORD PTR [ebp-0x8],0xd1
        <+31>:  cmp    DWORD PTR [ebp-0x8],0x5fa1
        <+38>:  jle    0x501 <asm2+20>
        <+40>:  mov    eax,DWORD PTR [ebp-0x4]
        <+43>:  leave  
        <+44>:  ret    

                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm2]
└─$ nano test.S 
                                                        
┌──(mino20㉿kali)-[~/Descargas/asm2]
└─$ cat test.S 
//simulacion
stack

[      ]<- esp
[      ]<- ebp - 0xc
[ 0xd5 ]<- ebp - 0x8
[ 0x2e ]<- ebp - 0x4
[ ebp  ]<- ebp 
[ ret  ]<- ebp + 0x4
[ 0x4  ]<- ebp + 0x8
[ 0x2d ]<- ebp + 0xc

registros
[ 0x4  ] eax

asm2: (0x4,0x2d)
..      <+0>:   push   ebp
..      <+1>:   mov    ebp,esp

..      <+3>:   sub    esp,0x10
..      <+6>:   mov    eax,DWORD PTR [ebp+0xc]
..      <+9>:   mov    DWORD PTR [ebp-0x4],eax
..      <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x50c <asm2+31>
..      <+20>:  add    DWORD PTR [ebp-0x4],0x1
..      <+24>:  add    DWORD PTR [ebp-0x8],0xd1
..      <+31>:  cmp    DWORD PTR [ebp-0x8],0x5fa1
        <+38>:  jle    0x501 <asm2+20>
        <+40>:  mov    eax,DWORD PTR [ebp-0x4]

        <+43>:  leave  
        <+44>:  ret

                                                                                                   
┌──(mino20㉿kali)-[~]
└─$ python
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x4 <= 0x5fa1
True
>>> hex(0x2d+0x1)
'0x2e'
>>> hex(0x4+0xd1)
'0xd5'
>>> 0xd5<=0x5fa1
True
>>> 0x5fa1/0xd1
117.13397129186603
>>> int(0x2d)
45
>>> hex(45+118)
'0xa3'
```
0xa3

## Notas
[condiciones](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm) de montaje

## Referencias
- []()