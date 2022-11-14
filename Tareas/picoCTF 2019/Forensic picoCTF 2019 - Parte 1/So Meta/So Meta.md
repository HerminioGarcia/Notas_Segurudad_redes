# So Meta

## Objetivo 
Descripción:
Encuentra la bandera en esta [imagen](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png) .

## Solución
usando exiftool podemos ver los metadatos y en los metadatos de la imgen viene la bandera
``` shell
┌──(mino20㉿kali)-[~/Descargas/So Meta]
└─$ ls
pico_img.png
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/So Meta]
└─$ open pico_img.png 
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/So Meta]
└─$ exiftool --help
Syntax:  exiftool [OPTIONS] FILE

Consult the exiftool documentation for a full list of options.
                                                                                                   
┌──(mino20㉿kali)-[~/Descargas/So Meta]
└─$ exiftool pico_img.png 
ExifTool Version Number         : 12.44
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2022:11:14 01:31:38-06:00
File Access Date/Time           : 2022:11:14 01:33:05-06:00
File Inode Change Date/Time     : 2022:11:14 01:31:48-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_eb36bf44}
Image Size                      : 600x600
Megapixels                      : 0.360
```

picoCTF{s0_m3ta_eb36bf44}

## Notas
¿Qué significa meta en el contexto de los archivos?

¿Has oído hablar de los metadatos?

## Referencias
sin referencias.