# WebNet1
## Objetivo
Encontramos esta [captura](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) y [clave](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key) de paquetes . Recuperar la bandera.

## Soluciòn
Usamos el mismo comando del reto anterior, analizamos la informaciòn y ahì encontraremos la flag.
```shell
┌──(mino20㉿kali)-[~/Descargas/WebNet1]
└─$ ls                                                  
capture.pcap  mystery  output  picopico.key
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/WebNet1]
└─$ ssldump -r capture.pcap -k picopico.key -d > output 
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/WebNet1]
└─$ ssldump -r capture.pcap -k picopico.key -d   
New TCP connection #1: 128.237.140.23(57930) <-> 172.31.22.220(443)
1 1  0.0297 (0.0297)  C>S  Handshake
      ClientHello
        Version 3.3 
        cipher suites
        TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_GCM_SHA384
        TLS_DH_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_RSA_WITH_AES_256_CBC_SHA256
        TLS_DH_DSS_WITH_AES_256_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_RSA_WITH_AES_256_CBC_SHA
        TLS_DH_DSS_WITH_AES_256_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_GCM_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA384
        TLS_ECDH_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_256_CBC_SHA
        TLS_RSA_WITH_AES_256_GCM_SHA384
        TLS_RSA_WITH_AES_256_CBC_SHA256
        TLS_RSA_WITH_AES_256_CBC_SHA
        TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_GCM_SHA256
        TLS_DH_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_RSA_WITH_AES_128_CBC_SHA256
        TLS_DH_DSS_WITH_AES_128_CBC_SHA256
        TLS_DHE_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_RSA_WITH_AES_128_CBC_SHA
        TLS_DH_DSS_WITH_AES_128_CBC_SHA
        TLS_ECDH_RSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_GCM_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256
        TLS_ECDH_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA
        TLS_RSA_WITH_AES_128_GCM_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA256
        TLS_RSA_WITH_AES_128_CBC_SHA
        TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_DHE_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_DH_DSS_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA
        TLS_RSA_WITH_3DES_EDE_CBC_SHA
        TLS_EMPTY_RENEGOTIATION_INFO_SCSV
        compression methods
                  NULL
        extensions
          server_name
              host_name: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
          ec_point_formats

          supported_groups

          session_ticket
          signature_algorithms
          heartbeat
          padding
        ja3 string:
```

picoCTF{honey.roasted.peanuts}

## Notas
Intente usar una herramienta como Wireshark.

¿Cómo se puede descifrar la transmisión TLS?

## Referencias