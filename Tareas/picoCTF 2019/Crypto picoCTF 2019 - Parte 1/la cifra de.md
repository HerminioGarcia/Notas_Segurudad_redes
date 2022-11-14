# la cifra de

## Objetivo 
Descripción:
Encontré este código en un libro viejo. ¿Puedes descifrar lo que dice? Conéctese con `nc jupiter.challenges.picoctf.org 58295`.

## Solución
Corremos el servidor
``` shell
┌──(mino20㉿kali)-[~/Descargas/caesar]
└─$ nc jupiter.challenges.picoctf.org 58295
Encrypted message:
Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3xf966878l}

Tnj qixxe wkqw-duhfmkseej ipsiwtpznzn uk l puqjarusahjeii htpnjc hubpvkw, hay rldk fcoaso 1467 be Qpot Gltzndtg Fwbkwei.

Zmp Volpnèxj Nivmpr ox ehkwpfuwp surptorps ifwlki ehk Fwbkwei Jndc uw Llhjcto Htpnjc.

It 1508, Ozhgsyey Ycizmpmozd itapnzjo tnj do-ifwlki eahzwa xjntg (f xazwtx uk dhokeej fwpnfmezx) ehgy hoaqo lgypr hj l cxneiifw curaotjyt uk ehk Atgksèce Inahkw.

Merqlsu’x deityd htzkrje avupaxjo it 1555 fd a itytosfaznzn uk ehk ktryy. Ehk qzwkw saraps uk ehk fwpnfmezx lrk szw ymtfzjo rklflgwwy, hze tnj llvmlbkyd ati ehk nydkc wezypry fce sniej gj mkfys uk l mtjxotnn kkd ahxfde, cmtcn hln hj oilkprkse woys eghs cuwceyuznjjyt.
```
vemos que es un cifrado Vigenere decode
lo intentamos resolver con ayda de la pagina CyberChef pegando el texto que nos dio el servidor
https://gchq.github.io/CyberChef/
pero nos falta la llave

![[Pasted image 20221109131936.png]]
al no tener la llave podemos usar otra pagina para intentar obtener esa llave por medio del texto dado por el servidor
nos dirigimos a https://www.guballa.de/vigenere-solver
![[Pasted image 20221109132621.png]]
en los resultados dados podemos ver cual era la llave e incluso podemos ve a la vandera
![[Pasted image 20221109132750.png]]
picoCTF{b311a50_0r_v1gn3r3_c1ph3ra966878a}

## Notas
Hay herramientas que hacen esto fácil.
Tal vez mirar la historia ayude

## Referencias
sin referencias.