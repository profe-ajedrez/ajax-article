# Uso de MySQLi para conectar un script PHP a MySQL

Sigue estos pasos para usar MySQLi para conectar un script PHP a MySQL:

Debes tener creada una base de datos.

Crea un Archivo nuevo haciendo clic en el icono del menú superior.
Guárdalo como `databaseconnect.php`. Puedes reemplazar el nombre con lo que quieras, solo asegúrate de estar usando php como extensión.
Haz doble clic para abrir el archivo y copia y pega las siguientes líneas de código en él. Cambia los primeros cuatro valores debajo de
`<?php` con las credenciales que anotaste anteriormente.

```php
<?php
$servername = "localhost";
$database = "databasename";
$username = "username";
$password = "password";
// Create connection
$conn = mysqli_connect($servername, $username, $password, $database);
// Check connection
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
echo "Connected successfully";
mysqli_close($conn);
```

## Explicación del código MySQLi
El método principal utilizado en este script es mysqli_connect(). Esta es una función interna de PHP para establecer una nueva conexión a un servidor MySQL.

Al comienzo de nuestro código, vemos pocas declaraciones de variables y valores asignados a esas variables. Por lo general, necesitamos cuatro variables para establecer una conexión adecuada: $servername, $database, $username y $password. En el código, hemos establecido los datos exactos de nuestra base de datos como valores para esas variables, así se pueden pasar a la función.

Si la conexión no es exitosa, se ejecuta la función die(). Esto básicamente termina con el script y arroja el mensaje de error de conexión establecido. De forma predeterminada, el error de conexión de MySQL dirá Connection failed seguido de un mensaje de error exacto que describe el problema.

Por otro lado, si la conexión MySQL es exitosa, el código imprimirá Connected successfully.

La última parte del código es mysqli_close, que simplemente permitirá cerrar la conexión a la base de datos manualmente. Si no se especifica, las conexiones MySQL se cerrarán por sí solas una vez que finalice el script.
