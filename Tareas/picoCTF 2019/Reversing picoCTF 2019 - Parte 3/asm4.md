# asm4
## Objetivo
¿Qué devolverá asm4("picoCTF_a3112")? Envíe la bandera como un valor hexadecimal (comenzando con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S)

## Solucion

```shell
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ file test.S
test.S: ASCII text

┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ file test.S
test.S: ASCII text
                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ cat test.S                           
asm4:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   push   ebx
        <+4>:   sub    esp,0x10
        <+7>:   mov    DWORD PTR [ebp-0x10],0x246
        <+14>:  mov    DWORD PTR [ebp-0xc],0x0
        <+21>:  jmp    0x518 <asm4+27>
        <+23>:  add    DWORD PTR [ebp-0xc],0x1
        <+27>:  mov    edx,DWORD PTR [ebp-0xc]
        <+30>:  mov    eax,DWORD PTR [ebp+0x8]
        <+33>:  add    eax,edx
        <+35>:  movzx  eax,BYTE PTR [eax]
        <+38>:  test   al,al
        <+40>:  jne    0x514 <asm4+23>
        <+42>:  mov    DWORD PTR [ebp-0x8],0x1
        <+49>:  jmp    0x587 <asm4+138>
        <+51>:  mov    edx,DWORD PTR [ebp-0x8]
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,edx
        <+59>:  movzx  eax,BYTE PTR [eax]
        <+62>:  movsx  edx,al
        <+65>:  mov    eax,DWORD PTR [ebp-0x8]
        <+68>:  lea    ecx,[eax-0x1]
        <+71>:  mov    eax,DWORD PTR [ebp+0x8]
        <+74>:  add    eax,ecx
        <+76>:  movzx  eax,BYTE PTR [eax]
        <+79>:  movsx  eax,al
        <+82>:  sub    edx,eax
        <+84>:  mov    eax,edx
        <+86>:  mov    edx,eax
        <+88>:  mov    eax,DWORD PTR [ebp-0x10]
        <+91>:  lea    ebx,[edx+eax*1]
        <+94>:  mov    eax,DWORD PTR [ebp-0x8]
        <+97>:  lea    edx,[eax+0x1]
        <+100>: mov    eax,DWORD PTR [ebp+0x8]
        <+103>: add    eax,edx
        <+105>: movzx  eax,BYTE PTR [eax]
        <+108>: movsx  edx,al
        <+111>: mov    ecx,DWORD PTR [ebp-0x8]
        <+114>: mov    eax,DWORD PTR [ebp+0x8]
        <+117>: add    eax,ecx
        <+119>: movzx  eax,BYTE PTR [eax]
        <+122>: movsx  eax,al
        <+125>: sub    edx,eax
        <+127>: mov    eax,edx
        <+129>: add    eax,ebx
        <+131>: mov    DWORD PTR [ebp-0x10],eax
        <+134>: add    DWORD PTR [ebp-0x8],0x1
        <+138>: mov    eax,DWORD PTR [ebp-0xc]
        <+141>: sub    eax,0x1
        <+144>: cmp    DWORD PTR [ebp-0x8],eax
        <+147>: jl     0x530 <asm4+51>
        <+149>: mov    eax,DWORD PTR [ebp-0x10]
        <+152>: add    esp,0x10
        <+155>: pop    ebx
        <+156>: pop    ebp
        <+157>: ret    

                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ nano solve.c
                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ cat test.S | cut -d ':' -f2                                

        push   ebp
        mov    ebp,esp
        push   ebx
        sub    esp,0x10
        mov    DWORD PTR [ebp-0x10],0x246
        mov    DWORD PTR [ebp-0xc],0x0
        jmp    0x518 <asm4+27>
        add    DWORD PTR [ebp-0xc],0x1
        mov    edx,DWORD PTR [ebp-0xc]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        test   al,al
        jne    0x514 <asm4+23>
        mov    DWORD PTR [ebp-0x8],0x1
        jmp    0x587 <asm4+138>
        mov    edx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    eax,DWORD PTR [ebp-0x8]
        lea    ecx,[eax-0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        mov    edx,eax
        mov    eax,DWORD PTR [ebp-0x10]
        lea    ebx,[edx+eax*1]
        mov    eax,DWORD PTR [ebp-0x8]
        lea    edx,[eax+0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    ecx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        add    eax,ebx
        mov    DWORD PTR [ebp-0x10],eax
        add    DWORD PTR [ebp-0x8],0x1
        mov    eax,DWORD PTR [ebp-0xc]
        sub    eax,0x1
        cmp    DWORD PTR [ebp-0x8],eax
        jl     0x530 <asm4+51>
        mov    eax,DWORD PTR [ebp-0x10]
        add    esp,0x10
        pop    ebx
        pop    ebp
        ret    

                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ nano solve.c               
                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ cat solve.c                
#include <stdio.h>
#include <stdlib.h>

int asm4(char* in){
        int val;
        asm(
        "nop;"
        "nop;"
        "nop;"
        //"push   ebp;"
        //"mov    ebp,esp;"
        "push   ebx;"
        "sub    esp,0x10"
        "mov    DWORD PTR [ebp-0x10],0x246"
        "mov    DWORD PTR [ebp-0xc],0x0"
        "jmp    _asm4_27;"
     "_asm_23:"
        "add    DWORD PTR [ebp-0xc],0x1;"
     "_asm_27:"
        "mov    edx,DWORD PTR [ebp-0xc];"
        "mov    eax,DWORD PTR [ebp+0x8];"
        "add    eax,edx;"
        "movzx  eax,BYTE PTR [eax];"
        "test   al,al;"
        "jne    _asm4_23;"
        "mov    DWORD PTR [ebp-0x8],0x1;"
        "jmp    _asm_138;"
     "_asm_51:"
        "mov    edx,DWORD PTR [ebp-0x8];"
        "mov    eax,DWORD PTR [ebp+0x8];"
        "add    eax,edx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  edx,al;"
        "mov    eax,DWORD PTR [ebp-0x8];"
        "lea    ecx,[eax-0x1];"
        "mov    eax,DWORD PTR [ebp+0x8];"
        "add    eax,ecx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  eax,al;"
        "sub    edx,eax;"
        "mov    eax,edx;"
        "mov    edx,eax;"
        "mov    eax,DWORD PTR [ebp-0x10];"
        "lea    ebx,[edx+eax*1];"
        "mov    eax,DWORD PTR [ebp-0x8];"
        "lea    edx,[eax+0x1];"
        "mov    eax,DWORD PTR [ebp+0x8];"
        "add    eax,edx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  edx,al;"
        "mov    ecx,DWORD PTR [ebp-0x8];"
        "mov    eax,DWORD PTR [ebp+0x8];"
        "add    eax,ecx;"
        "movzx  eax,BYTE PTR [eax];"
        "movsx  eax,al;"
        "sub    edx,eax;"
        "mov    eax,edx;"
        "add    eax,ebx;"
        "mov    DWORD PTR [ebp-0x10],eax;"
        "add    DWORD PTR [ebp-0x8],0x1;"
     "_asm_138:"
        "mov    eax,DWORD PTR [ebp-0xc];"
        "sub    eax,0x1;"
        "cmp    DWORD PTR [ebp-0x8],eax;"
        "jl     _asm_51;"
        "mov    eax,DWORD PTR [ebp-0x10];"
        "add    esp,0x10;"
        "pop    ebx;"
        //"pop    ebp;"
        //"ret  ;"
        "nop;"
        "nop;"
        "nop;"
                :"=r"(val)
                : [pInput] "m"(in)
        );

        return val;
}
                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ nano solve.c
                                                                   
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ gcc -masm=intel -m32 solve.c -o solve
In file included from solve.c:1:
/usr/include/stdio.h:27:10: fatal error: bits/libc-header-start.h: No such file or directory
   27 | #include <bits/libc-header-start.h>
      |          ^~~~~~~~~~~~~~~~~~~~~~~~~~
compilation terminated.
```

## Notas
Tratar el argumento Array como un puntero

## Referencias
- []()