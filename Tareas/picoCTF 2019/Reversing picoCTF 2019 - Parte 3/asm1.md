# asm1
## Objetivo
¿Qué devuelve asm1 (0x2e0)? Envíe la bandera como un valor hexadecimal (comenzando con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/f1c2358ff7d1e9386e41552c549cf2f6/test.S)

## Solucion
descargamos el codigo
```shell
┌──(mino20㉿kali)-[~/Descargas/asm1]
└─$ ls                               
test.S
                                                                                                   
//vemos de que se trata
┌──(mino20㉿kali)-[~/Descargas/asm1]
└─$ file test.S 
test.S: ASCII text
                                                                                                   
veos la estructura de registros creo es de intel de 34
┌──(mino20㉿kali)-[~/Descargas/asm1]
└─$ cat test.S    
asm1:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   cmp    DWORD PTR [ebp+0x8],0x3fb
        <+10>:  jg     0x512 <asm1+37>
        <+12>:  cmp    DWORD PTR [ebp+0x8],0x280
        <+19>:  jne    0x50a <asm1+29>
        <+21>:  mov    eax,DWORD PTR [ebp+0x8]
        <+24>:  add    eax,0xa
        <+27>:  jmp    0x529 <asm1+60>
        <+29>:  mov    eax,DWORD PTR [ebp+0x8]
        <+32>:  sub    eax,0xa
        <+35>:  jmp    0x529 <asm1+60>
        <+37>:  cmp    DWORD PTR [ebp+0x8],0x559
        <+44>:  jne    0x523 <asm1+54>
        <+46>:  mov    eax,DWORD PTR [ebp+0x8]
        <+49>:  sub    eax,0xa
        <+52>:  jmp    0x529 <asm1+60>
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,0xa
        <+60>:  pop    ebp
        <+61>:  ret    
esto es como un espacio de la memoria y funciona coo una pila
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm1]
└─$ nano stack        
simulamos
stack

0000


[ebp] <- esp <-ebp (ebp ya no se muebe) 
[ret] <- para acceder al primer parametro ebp +0x4 
[0x2e0] <- ebp + 0x8 
fffff

registers
[0x2d6] <- eax

asm1:
..      <+0>:   push   ebp
..      <+1>:   mov    ebp,esp
        
..      <+3>:   cmp    DWORD PTR [ebp+0x8],0x3fb
        <+10>:  jg     0x512 <asm1+37>
        <+12>:  cmp    DWORD PTR [ebp+0x8],0x280
        <+19>:  jne    0x50a <asm1+29>
        <+21>:  mov    eax,DWORD PTR [ebp+0x8]
        <+24>:  add    eax,0xa
        <+27>:  jmp    0x529 <asm1+60>
        <+29>:  mov    eax,DWORD PTR [ebp+0x8]
        <+32>:  sub    eax,0xa
        <+35>:  jmp    0x529 <asm1+60>
..      <+37>:  0x2e00x2e0cmp    DWORD PTR [ebp+0x8],0x559
..      <+44>:  jne    0x523 <asm1+54>
..      <+46>:  mov    eax,DWORD PTR [ebp+0x8]
..      <+49>:  sub    eax,0xa
..      <+52>:  jmp    0x529 <asm1+60>
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,0xa
        
        <+60>:  pop    ebp
        <+61>:  ret

                                                                                                   
┌──(mino20㉿kali)-[~]
└─$ python 
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x3fb > 0x2e0
True
>>> 0x2e0== 0x559
False
>>> 0x2e0 - 0xa
726
>>> hex(0x2e0 - 0xa)
'0x2d6'
>>>
```


## Notas
[condiciones](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm) de montaje

## Referencias
- []()