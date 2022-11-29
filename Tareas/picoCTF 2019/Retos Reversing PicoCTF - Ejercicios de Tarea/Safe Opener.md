# Safe Opener
## Objetivo
¿Puedes abrir esta caja fuerte?Olvidé la llave de mi caja fuerte, pero se supone que este [programa me ayude a recuperar la llave perdida.](https://artifacts.picoctf.net/c/463/SafeOpener.java) ¿Puedes ayudarme a desbloquear mi caja fuerte?Ponga la contraseña que recupere en el formato de bandera picoCTF como:`picoCTF{password}`

## Solucion

```shell

┌──(mino20㉿kali)-[~/Descargas/SafeOpener]
└─$ ls
'01- file-run1.md'  '03- GDB Test Drive.md'  '05- Safe Opener.md'     SafeOpener.java
'02- file-run2.md'  '04- patchme.py.md'      Help-pictures-notes

┌──(mino20㉿kali)-[~/Descargas/SafeOpener]
└─$ file SafeOpener.java
SafeOpener.java: Java source, ASCII text

┌──(mino20㉿kali)-[~/Descargas/SafeOpener]
└─$ cat SafeOpener.java
import java.io.*;
import java.util.*;  
public class SafeOpener {
    public static void main(String args[]) throws IOException {
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        int i = 0;
        boolean isOpen;
        

        while (i < 3) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();

            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
              
            isOpen = openSafe(encodedkey);
            if (!isOpen) {
                System.out.println("You have  " + (2 - i) + " attempt(s) left");
                i++;
                continue;
            }
            break;
        }
    }
    
    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";
        
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        else {
            System.out.println("Password is incorrect\n");
            return false;
        }
    }
}  

┌──(mino20㉿kali)-[~/Descargas/SafeOpener]
└─$ echo "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz" | base64 -d     
pl3as3_l3t_m3_1nt0_th3_saf3     
```

picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}

## Notas
ninguno

## Referencias
sin referencias.