# vault-door-3

## Objetivo 
Descripción:
Esta bóveda utiliza bucles for y matrices de bytes. El código fuente de esta bóveda está aquí: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/943ea40e3f54fca6d2145fa7aadc5e09/VaultDoor3.java)

## Solución
Usaremos java scrip para resolver el reto 
``` shell
┌──(mino20㉿kali)-[~]
└─$ cd Descargas/vault-door-3
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/vault-door-3]
└─$ ls
VaultDoor3.java
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/vault-door-3]
└─$ cat VaultDoor3.java      
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just know this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm18g947_u_4_m9r54f");
    }
}
//vemos de donde se optiene la contraseña
//usaremos java scrip para poder resolver el reto
```
![[Pasted image 20221109073418.png]]
ahora para poder comprobar si es la vandera simplemente la probamos en el programa java
``` shell
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/vault-door-3]
└─$ javac VaultDoor3.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                               
┌──(mino20㉿kali)-[~/Descargas/vault-door-3]
└─$ java VaultDoor3                         
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}
Access granted.
```

## Notas
Cree una tabla que contenga cada valor de las variables de bucle y el índice de búfer correspondiente en el que escribe.

## Referencias
sin referencias.