## waves over lambda

## Objetivo 
Descripción:
Hicimos muchas sustituciones para cifrar esto. ¿Puedes descifrarlo? Conéctese con `nc jupiter.challenges.picoctf.org 13758`.

## Solución
Corremos el servidor
``` shell
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ nc jupiter.challenges.picoctf.org 13758  
-------------------------------------------------------------------------------
udqmxgej lsxs wj bdhx pvgm - pxsfhsqub_wj_u_dosx_vgzirg_rqoepxegbh
-------------------------------------------------------------------------------
gvscsb pbdrdxdoweul ngxgzgkdo agj els elwxr jdq dp pbdrdx ygovdoweul ngxgzgkdo, g vgqr daqsx asvv nqdaq wq dhx rwjexwue wq lwj daq rgb, gqr jewvv xszszisxsr gzdqm hj dawqm ed lwj mvddzb gqr exgmwu rsgel, alwul lgyysqsr elwxessq bsgxj gmd, gqr alwul w jlgvv rsjuxwis wq wej yxdysx yvgus. pdx els yxsjsqe w awvv dqvb jgb elge elwj vgqrdaqsxpdx jd as hjsr ed ugvv lwz, gveldhml ls lgxrvb jysqe g rgb dp lwj vwps dq lwj daq sjegesagj g jexgqms ebys, bse dqs yxseeb pxsfhsqevb ed is zse awel, g ebys gitsue gqr owuwdhj gqr ge els jgzs ewzs jsqjsvsjj. ihe ls agj dqs dp eldjs jsqjsvsjj ysxjdqj ald gxs osxb asvv ugygivs dp vddnwqm gpesx elswx adxvrvb gppgwxj, gqr, gyygxsqevb, gpesx qdelwqm svjs. pbdrdx ygovdoweul, pdx wqjegqus, ismgq awel qsce ed qdelwqm; lwj sjeges agj dp els jzgvvsje; ls xgq ed rwqs ge delsx zsq'j egivsj, gqr pgjesqsr dq elsz gj g edgrb, bse ge lwj rsgel we gyysgxsr elge ls lgr g lhqrxsr eldhjgqr xdhivsj wq lgxr ugjl. ge els jgzs ewzs, ls agj gvv lwj vwps dqs dp els zdje jsqjsvsjj, pgqegjewugv psvvdaj wq els aldvs rwjexwue. w xsysge, we agj qde jehywrwebels zgtdxweb dp elsjs pgqegjewugv psvvdaj gxs jlxsar gqr wqesvvwmsqe sqdhmlihe thje jsqjsvsjjqsjj, gqr g ysuhvwgx qgewdqgv pdxz dp we.'
                                                                                                  
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ sudo apt install xclip
[sudo] contraseña para mino20: 
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes NUEVOS:
  xclip
0 actualizados, 1 nuevos se instalarán, 0 para eliminar y 544 no actualizados.
Se necesita descargar 23.3 kB de archivos.
Se utilizarán 65.5 kB de espacio de disco adicional después de esta operación.
Des:1 http://kali.download/kali kali-rolling/main amd64 xclip amd64 0.13-2 [23.3 kB]
Descargados 23.3 kB en 1s (28.5 kB/s)
Seleccionando el paquete xclip previamente no seleccionado.
(Leyendo la base de datos ... 311832 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../xclip_0.13-2_amd64.deb ...
Desempaquetando xclip (0.13-2) ...
Configurando xclip (0.13-2) ...
Procesando disparadores para man-db (2.10.2-1) ...
Procesando disparadores para kali-menu (2022.3.1) ...
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ nc jupiter.challenges.picoctf.org 13758 | xclip -selection c
```
vemos que se trata de un cifrado substitution, necesitamos una llave asi que nos dirigimos a https://www.guballa.de/substitution-solver para poder entrar de forma bruta y obtener la bandera
![[Pasted image 20221109151519.png]]
en el resultado vemos que nos da la bandera
![[Pasted image 20221109151603.png]]

recuerda que esta bandera no tiene el formato habitual

## Notas
La bandera no tiene el formato de bandera habitual

## Referencias
sin referencias.