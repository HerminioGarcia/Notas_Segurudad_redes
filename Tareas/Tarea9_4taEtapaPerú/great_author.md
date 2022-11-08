# great_author

## Soluciòn
para encontrar oliver_twist.txt usamos find . oliver_twist.txt 
```shell
┌──(kiriha㉿kali)-[~/Escritorio/MetaCTF/great_author]
└─$ find . oliver_twist.txt                 
.
./adequate_books
./adequate_books/more_books
./adequate_books/more_books/.secret
./adequate_books/more_books/.secret/deeper_secrets
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/Oliver_Twist.txt
./adequate_books/more_books/1023.txt.utf-8
./adequate_books/46804-0.txt
./adequate_books/44578.txt.utf-8
./satisfactory_books
./satisfactory_books/more_books
./satisfactory_books/more_books/37121.txt.utf-8
./satisfactory_books/16021.txt.utf-8
./satisfactory_books/23765.txt.utf-8
./14789.txt.utf-8
./13771.txt.utf-8
./acceptable_books
./acceptable_books/17880.txt.utf-8
./acceptable_books/more_books
./acceptable_books/more_books/40723.txt.utf-8
./acceptable_books/17879.txt.utf-8
find: ‘oliver_twist.txt’: No existe el fichero o el directorio
                                                                                                                                                                      
┌──(kiriha㉿kali)-[~/Escritorio/MetaCTF/great_author]
└─$ cd ./adequate_books/more_books/.secret/deeper_secrets 
                                                                                                                                                                      
┌──(kiriha㉿kali)-[~/…/adequate_books/more_books/.secret/deeper_secrets]
└─$ ls                                                   
deepest_secrets
                                                                                                                                                                      
┌──(kiriha㉿kali)-[~/…/adequate_books/more_books/.secret/deeper_secrets]
└─$ cd deepest_secrets                                   
                                                                                                                                                                      
┌──(kiriha㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ ls
Oliver_Twist.txt
                                                                                                                                                                      
┌──(kiriha㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ cat Oliver_Twist.txt 
fl@g{Ch@rRl3$_D1cK3N$}

```

## Referencias
sin refere