# Nice netcat

## Objetivo 
Descripción:
Hay un buen programa con el que puedes hablar usando este comando en un shell: `$ nc mercury.picoctf.net 49039`, pero no habla inglés...

Sugerencias:
Puedes practicar el uso de netcat con este problema de picoGym: [¿qué es un netcat?](https://play.picoctf.org/practice/challenge/34)

Puedes practicar la lectura y escritura ASCII con este problema de picoGym: [Vamos a calentar](https://play.picoctf.org/practice/challenge/22)

## Solución 
``` shell
┌──(mino20㉿kali)-[~]
└─$ nc mercury.picoctf.net 49039
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
51 
100 
56 
52 
101 
100 
99 
56 
125 
10

// aqui usare un comvertidor web para transformar ASCII a texto

//https://es.rakko.tools/tools/76/

picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}
```

## Notas
para entrar solo recuerda el servidor y el puerto
nc jupiter.challenges.picoctf.org 25103
tambien podemos usar erramientas externas para resolver los retos

## Referencias
[nc](https://linux.die.net/man/1/nc)
[convertidor de binario y hexadecimal](https://www.rapidtables.com/convert/number/binary-to-ascii.html)
[convertidor de octal](http://www.unit-conversion.info/texttools/octal/)[convertidor de ASCII A TEXTO](https://es.rakko.tools/tools/76/)