# asm3
## Objetivo
¿Qué devuelve asm3 (0xd73346ed, 0xd48672ae, 0xd3c8b139)? Envíe la bandera como un valor hexadecimal (comenzando con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S)

## Solucion
![[Pasted image 20221129024027.png]]

```shell
┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ file test.S
test.S: ASCII text

┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$ cat test.S
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0xa]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xc]
        <+15>:  add    ah,BYTE PTR [ebp+0xd]
        <+18>:  xor    ax,WORD PTR [ebp+0x10]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret    

┌──(mino20㉿kali)-[~/Descargas/asm3]
└─$
```

bandera: 0xC36B

## Notas
más (?) [registros](https://wiki.skullsecurity.org/index.php?title=Registers)

## Referencias
- []()