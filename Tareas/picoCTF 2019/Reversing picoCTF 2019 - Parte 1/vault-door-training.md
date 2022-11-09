# vault-door-training

## Objetivo 
Descripción:
Tu misión es ingresar al laboratorio del Dr. Evil y recuperar los planos para su Proyecto Doomsday. El laboratorio está protegido por una serie de puertas de bóveda cerradas. Cada puerta está controlada por una computadora y requiere una contraseña para abrirse. Desafortunadamente, nuestros agentes encubiertos no han podido obtener las contraseñas secretas de las puertas de las bóvedas, ¡pero uno de nuestros agentes subalternos obtuvo el código fuente de la computadora de cada bóveda! Deberá leer el código fuente de cada nivel para averiguar cuál es la contraseña para esa puerta de la bóveda. Como calentamiento, hemos creado una bóveda de réplica en nuestro centro de entrenamiento. El código fuente de la bóveda de entrenamiento está aquí: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java)

## Solución
``` shell
┌──(mino20㉿kali)-[~]
└─$ cd Descargas/vault-door-training 
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/vault-door-training]
└─$ cat VaultDoorTraining.java      
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
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

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
    }
}

picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}
```

## Notas
La contraseña se revela en el código fuente del programa.

## Referencias
sin referencias.