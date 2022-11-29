# vault-door-5
## Objetivo
En el último desafío, dominaste los números octales (base 8), decimales (base 10) y hexadecimales (base 16), ¡pero esta puerta de bóveda usa un cambio de base diferente, así como la codificación de URL! El código fuente de esta bóveda está aquí: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)

## Solucion
```shell
┌──(mino20㉿kali)-[~/Descargas/vault-door-5]
└─$ ls
'01- vault-door-training.md'  '05- vault-door-5.md'  '09- asm3.md'            '13- B1ll_Gat35.md'    VaultDoor3.class   VaultDoor5.java
'02- vault-door-1.md'         '06- vault-door-6.md'  '10- asm4.md'             flag                  VaultDoor3.java    VaultDoorTraining.java
'03- vault-door-3.md'         '07- asm1.md'          '11- reverse_cipher.md'   Help-pictures-notes   VaultDoor4.class
'04- vault-door-4.md'         '08- asm2.md'          '12- Need For Speed.md'   VaultDoor1.java       VaultDoor4.java

┌──(mino20㉿kali)-[~/Descargas/vault-door-4]
└─$ file VaultDoor5.java
VaultDoor5.java: C++ source, ASCII text

┌──(mino20㉿kali)-[~/Descargas/vault-door-4]
└─$ cat VaultDoor5.java
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
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

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that''s what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
        return base64Encoded.equals(expected);
    }
}

```


JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0


![[Pasted image 20221128232054.png]]

%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%65%33%31%35%32%62%66%34


![[Pasted image 20221128232213.png]]
c0nv3rt1ng_fr0m_ba5e_64_e3152bf4
con eso tenemos la bandera
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}

## Notas
Puede encontrar util una herramienta codificadora/descodificadora, como https://encoding.tools/

Lea los artículos de wikipedia sobre la codificacion de URL y la codificación de base 64 para comprender cómo funcionan y cómo se ven los resultados.

## Referencias
- []()