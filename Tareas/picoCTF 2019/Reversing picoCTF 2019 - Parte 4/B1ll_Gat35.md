# B1ll_Gat35
## Objetivo
¿Puedes revertir este [binario de Windows](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe) ?

## Solucion
descargamos los datos
```shell
┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ ls
'01- vault-door-training.md'  '04- vault-door-4.md'  '07- asm1.md'  '10- asm4.md'            '13- B1ll_Gat35.md'    miProyec.lock    need-for-speed 
'02- vault-door-1.md'         '05- vault-door-5.md'  '08- asm2.md'  '11- reverse_cipher.md'   Help-pictures-notes   miProyec.lock~   test.S
'03- vault-door-3.md'         '06- vault-door-6.md'  '09- asm3.md'  '12- Need For Speed.md'   miProyec.gpr          miProyec.rep     win-exec-1.exe

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ file win-exec-1.exe
win-exec-1.exe: PE32 executable (console) Intel 80386, for MS Windows

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ wine win-exec-1.exe     
Input a number between 1 and 5 digits: 1
Initializing...
Enter the correct key to get the access codes: 1234
Incorrect key. Try again.

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ ghidra &                     
[1] 43129

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

[1]  + done       ghidra
┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ 
```

![[Pasted image 20221129044256.png]]

![[Pasted image 20221129044401.png]]

![[Pasted image 20221129044610.png]]

![[Pasted image 20221129044738.png]]

![[Pasted image 20221129045011.png]]

![[Pasted image 20221129045220.png]]

![[Pasted image 20221129045315.png]]

![[Pasted image 20221129045406.png]]

![[Pasted image 20221129045521.png]]

![[Pasted image 20221129045605.png]]

![[Pasted image 20221129045649.png]]

```shell
┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ ls                  
'01- vault-door-training.md'  '04- vault-door-4.md'  '07- asm1.md'  '10- asm4.md'            '13- B1ll_Gat35.md'    miProyec.rep     win-exec-1.exe
'02- vault-door-1.md'         '05- vault-door-5.md'  '08- asm2.md'  '11- reverse_cipher.md'   Help-pictures-notes   need-for-speed   win-exec-2.exe.bin
'03- vault-door-3.md'         '06- vault-door-6.md'  '09- asm3.md'  '12- Need For Speed.md'   miProyec.gpr          test.S

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ mv win-exec-2.exe.bin win-exec-2.exe

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ ls                  
'01- vault-door-training.md'  '04- vault-door-4.md'  '07- asm1.md'  '10- asm4.md'            '13- B1ll_Gat35.md'    miProyec.rep     win-exec-1.exe
'02- vault-door-1.md'         '05- vault-door-5.md'  '08- asm2.md'  '11- reverse_cipher.md'   Help-pictures-notes   need-for-speed   win-exec-2.exe
'03- vault-door-3.md'         '06- vault-door-6.md'  '09- asm3.md'  '12- Need For Speed.md'   miProyec.gpr          test.S

┌──(mino20㉿kali)-[~/Descargas/B1ll_Gat35]
└─$ wine win-exec-2.exe
Input a number between 1 and 5 digits: 1
Initializing...
Enter the correct key to get the access codes: 1234
Correct input. Printing flag: PICOCTF{These are the access codes to the vault: 1063340}
```
PICOCTF{These are the access codes to the vault: 1063340}

## Notas
Microsoft proporciona máquinas virtuales de Windows https://developer.microsoft.com/en-us/windows/downloads/virtual-machines

Ollydbg puede ser útil

Formato de bandera: PICOCTF{XXXX}

## Referencias
- []()