# logon

## Objetivo 
La fábrica está escondiendo cosas de todos sus usuarios. ¿Puede iniciar sesión como Joe y encontrar lo que han estado mirando? `https://jupiter.challenges.picoctf.org/problem/15796/`( [enlace](https://jupiter.challenges.picoctf.org/problem/15796/) ) o http://jupiter.challenges.picoctf.org:15796

## Solución
nos dirigimos a la pagina
e intentamos logiarnos con joe con cualquier contraseña
![[Pasted image 20221128040141.png]]

![[Pasted image 20221128040155.png]]

intentamos logearnos con otro usuario
![[Pasted image 20221128040234.png]]
![[Pasted image 20221128040252.png]]

abrimos el inspector y nos dirigimos a nerwork
![[Pasted image 20221128040517.png]]

intentamos logearnos y podemos ver las peticiones
![[Pasted image 20221128040653.png]]

podemos tambien ver los HTTP headers
![[Pasted image 20221128041445.png]]

nos podemos dirigir al Request Heders y podemos ver que se encuentra una cookie 
![[Pasted image 20221128042051.png]]

tambien podemos ver los cookies con los datos que quisimos mandar
![[Pasted image 20221128042303.png]]
podemos notar que el admin esta en falso asi que lo proximo a realizar seria la comvercion a true

intentamos editar esa cookie admin pero notamos que esta protegida

asi que prosedemos a descargar cooki Editor

una ves descargado podemos editar las cookie que mandamos anterior mente

![[Pasted image 20221128042930.png]]

editamos y guardamos
![[Pasted image 20221128043013.png]]
y simplemente recargamos

![[Pasted image 20221128043106.png]]
## Notas
Hmm, parece que no verifica la contraseña de nadie, excepto la de Joe.

## Referencias
sin referencias.