# vault-door-4

## Objetivo 
Descripción:
Esta bóveda usa codificación ASCII para la contraseña. El código fuente de esta bóveda está aquí: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java)

## Solución
Usaremos java scrip para resolver el reto para trasformar todo a texto normal
``` shell
┌──(mino20㉿kali)-[~/Descargas]
└─$ cd vault-door-4
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/vault-door-4]
└─$ ls
VaultDoor4.java
                                                                                               
//analizamos el codigo
┌──(mino20㉿kali)-[~/Descargas/vault-door-4]
└─$ cat VaultDoor4.java
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just know that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
            '4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
                                                                                               
```
![[Pasted image 20221109080704.png]]
``` shell
// probamos la bandera
┌──(mino20㉿kali)-[~/Descargas/vault-door-4]
└─$ javac VaultDoor4.java                    
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/vault-door-4]
└─$ java VaultDoor4      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}
Access granted.
```

## Notas
Utilice un motor de búsqueda para encontrar una "tabla ASCII".

También necesitará saber la diferencia entre números octales, decimales y hexadecimales.

## Referencias
sin referencias.