# dont-use-client-side

## Objetivo 
¿Puedes entrar en este portal súper seguro? `https://jupiter.challenges.picoctf.org/problem/29835/`( [enlace](https://jupiter.challenges.picoctf.org/problem/29835/) ) o http://jupiter.challenges.picoctf.org:29835

## Solución
nos dirigimos a la pagina y ponemos cualquier contraseña
![[Pasted image 20221128045149.png]]
![[Pasted image 20221128045228.png]]
vemos que la contraseña es incorrecta

entonces nos dirigimos al inspector y luego al debuger donde podemos ver el codigo index 



ahora hasta arriba hay unos link uno de css y uno de js y si nos vamos a ellos encontraremos las partes faltantes de la bandera

![[Pasted image 20221128045440.png]]

y simplemente lo acomodamos

``` shell
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }



picoCTF{no_clients_plz_7723ce}
```
## Notas
Nunca confíes en el cliente.

## Referencias
sin referencias.