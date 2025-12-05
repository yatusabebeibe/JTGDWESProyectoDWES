# **Estudio clases y funciones**

- [**Estudio clases y funciones**](#estudio-clases-y-funciones)
  - [**Mas importantes**](#mas-importantes)
    - [Funciones](#funciones)
      - [`is_null()`](#is_null)
      - [`empty()`](#empty)
      - [`isset()`](#isset)
      - [`date()`](#date)
      - [`var_dump()`](#var_dump)
      - [`nl2br()`](#nl2br)
      - [`htmlspecialchars()`](#htmlspecialchars)
      - [`list()`](#list)
      - [`json_encode()`](#json_encode)
      - [`json_decode()`](#json_decode)
      - [`file_put_contents()`](#file_put_contents)
      - [`basename()`](#basename)
      - [`header()`](#header)
    - [Clases](#clases)
      - [`DateTime`](#datetime)
      - [`PDO`](#pdo)
      - [`PDOStatement`](#pdostatement)
      - [`PDOException`](#pdoexception)
      - [`DOMDocument`](#domdocument)
  - [**General**](#general)
    - [**Salida De Texto**](#salida-de-texto)
    - [**Tipos Y Variables**](#tipos-y-variables)
    - [**Constantes**](#constantes)
    - [**Fechas Y Horas**](#fechas-y-horas)
    - [**Inclusión De Archivos**](#inclusión-de-archivos)
    - [**Punteros De Arrays**](#punteros-de-arrays)
    - [**Manejo De Arrays**](#manejo-de-arrays)
    - [**Otras Funciones**](#otras-funciones)
    - [**PDO (Base de datos)**](#pdo-base-de-datos)
      - [**Transacciones**](#transacciones)
      - [**Consultas preparadas**](#consultas-preparadas)
    - [**JSON**](#json)
    - [**XML**](#xml)
    - [**Cabeceras HTTP**](#cabeceras-http)
    - [**DOMDocument (Manipulación de XML/HTML)**](#domdocument-manipulación-de-xmlhtml)

## **Mas importantes**

### Funciones

| Función                                     | Explicación                                                                          | Retorna   |
| ------------------------------------------- | ------------------------------------------------------------------------------------ | --------- |
| [`is_null()`](#is_null)                     | Comprueba si una variable es **exactamente** `NULL`                                  | bool      |
| [`empty()`](#empty)                         | Comprueba si una variable está vacía (`""`, `0`, `null`, `false`, `[]`, etc.)        | bool      |
| [`isset()`](#isset)                         | Comprueba si una variable **existe** y **no** es `NULL`                              | bool      |
| [`date()`](#date)                           | Genera una fecha/hora formateada según el formato que indiques                       | string    |
| [`var_dump()`](#var_dump)                   | Muestra el tipo de dato y el valor con todo detalle                                  | void      |
| [`nl2br()`](#nl2br)                         | Convierte saltos de línea `\n` en etiquetas `<br>`                                   | string    |
| [`htmlspecialchars()`](#htmlspecialchars)   | Convierte caracteres especiales en entidades HTML para evitar problemas de seguridad | string    |
| [`list()`](#list)                           | Extrae valores de un array asignándolos a variables en orden                         | array     |
| [`json_encode()`](#json_encode)             | Convierte un dato de PHP a formato JSON                                              | string    |
| [`json_decode()`](#json_decode)             | Convierte texto JSON a una variable PHP                                              | mixed     |
| [`file_put_contents()`](#file_put_contents) | Escribe datos en un archivo (lo crea si no existe)                                   | int|false |
| [`basename()`](#basename)                   | Obtiene solo el nombre de un archivo a partir de su ruta                             | string    |
| [`header()`](#header)                       | Envía una cabecera HTTP al navegador (redirecciones, tipo de contenido, etc.)        | void      |

#### `is_null()`

Devuelve true solo si la variable es exactamente `NULL`.
Ejemplo:

```php
$a = null;
is_null($a); // true
```

No sirve para comprobar si una variable existe.

---

#### `empty()`

Devuelve true si la variable está vacía: `""`, `0`, `"0"`, `null`, `false`, `[]` o si no existe.
Ejemplo:

```php
empty(""); // true
empty(0);  // true
```

Ten en cuenta que considera `0` como vacío.

---

#### `isset()`

Devuelve true si la variable existe y no es `NULL`.
Ejemplo:

```php
$a = 0;
isset($a); // true
```

A diferencia de `empty`, no considera `0` como vacío.

---

#### `date()`

Devuelve una fecha/hora formateada según el formato indicado.
Ejemplo:

```php
echo date('Y-m-d H:i:s');
```

Usa la zona horaria configurada en PHP.

---

#### `var_dump()`

Muestra el tipo de dato y su valor.
Ejemplo:

```php
var_dump([1, "a", true]);
```

Es útil para depurar código.

---

#### `nl2br()`

Convierte saltos de línea `\n` en `<br>`.
Ejemplo:

```php
echo nl2br("hola\nmundo");
```

Útil cuando muestras texto en HTML que proviene de formularios.

---

#### `htmlspecialchars()`

Convierte caracteres especiales en entidades HTML.
Ejemplo:

```php
echo htmlspecialchars('<b>hola</b>');
```

Evita que se ejecuten etiquetas HTML enviadas por el usuario.

---

#### `list()`

Extrae valores de un array y los asigna a variables en orden.
Ejemplo:

```php
list($a, $b) = [10, 20];
```

Solo funciona con arrays indexados numéricamente.

---

#### `json_encode()`

Convierte datos de PHP a formato JSON.
Ejemplo:

```php
json_encode(['a' => 1]);
```

Ideal para enviar datos a JavaScript.

---

#### `json_decode()`

Convierte JSON en una variable PHP.
Ejemplo:

```php
json_decode('{"a":1}', true);
```

Con `true` devuelve un array asociativo.

---

#### `file_put_contents()`

Escribe datos en un archivo.
Ejemplo:

```php
file_put_contents('log.txt', "hola\n", FILE_APPEND);
```

Si el archivo no existe, lo crea.

---

#### `basename()`

Devuelve el nombre del archivo desde una ruta.
Ejemplo:

```php
basename('/var/www/index.php'); // index.php
```

Si quieres más información del archivo, puedes usar `pathinfo()`.

---

#### `header()`

Envía una cabecera HTTP al navegador.
Ejemplo:

```php
header('Location: login.php');
exit;
```

Debe usarse antes de enviar cualquier salida al navegador.

### Clases

| Clase                           | Explicación                                                           | Métodos clave                                              |
| ------------------------------- | --------------------------------------------------------------------- | ---------------------------------------------------------- |
| [`DateTime`](#datetime)         | Permite crear, modificar y formatear fechas y horas de forma avanzada | `format()`, `modify()`, `add()`, `diff()`                  |
| [`PDO`](#pdo)                   | Maneja la conexión a una base de datos y operaciones principales      | `prepare()`, `query()`, `exec()`, `beginTransaction()`     |
| [`PDOStatement`](#pdostatement) | Representa una consulta preparada lista para ejecutar                 | `execute()`, `fetch()`, `fetchAll()`, `rowCount()`         |
| [`PDOException`](#pdoexception) | Excepción que se lanza cuando ocurre un error con PDO                 | `getMessage()`, `getCode()`                                |
| [`DOMDocument`](#domdocument)   | Permite crear, leer y modificar documentos XML o HTML                 | `load()`, `loadHTML()`, `save()`, `getElementsByTagName()` |

#### `DateTime`

Permite crear, modificar y formatear fechas de forma avanzada.
Ejemplo:

```php
$d = new DateTime('2025-12-05 10:00');
$d->modify('+1 day');
echo $d->format('Y-m-d');
```

Útil para sumar/restar días o comparar fechas.

---

#### `PDO`

Maneja la conexión y las operaciones con bases de datos.
Ejemplo:

```php
$pdo = new PDO('mysql:host=localhost;dbname=test', 'user', 'pass');
$stmt = $pdo->prepare("SELECT * FROM tabla");
$stmt->execute();
```

Permite usar consultas preparadas para mayor seguridad.

---

#### `PDOStatement`

Representa una consulta preparada lista para ejecutar.
Ejemplo:

```php
$stmt = $pdo->prepare("SELECT * FROM usuarios WHERE id = :id");
$stmt->execute(['id' => 1]);
$row = $stmt->fetch();
```

`fetchAll()` obtiene todas las filas como array.

---

#### `PDOException`

Excepción que se lanza cuando ocurre un error con PDO.
Ejemplo:

```php
try {
    $pdo = new PDO($dsn, $user, $pass);
} catch (PDOException $e) {
    echo $e->getMessage();
}
```

Permite capturar errores de conexión o consultas.

---

#### `DOMDocument`

Permite crear, leer y modificar documentos XML o HTML.
Ejemplo:

```php
$doc = new DOMDocument();
$doc->loadHTML('<p>Hola</p>');
$tags = $doc->getElementsByTagName('p');
```

Puedes modificar nodos y luego guardar el resultado.

## **General**

### **Salida De Texto**
- **echo** → imprime texto.
- **print** → imprime texto (devuelve 1).
- **printf** → imprime con formato.
- **sprintf** → igual que printf pero devuelve el texto en vez de imprimirlo.
- **print_r** → muestra estructuras (arrays/objetos) de forma legible.
- **var_dump** → muestra información detallada (tipo y valor).

---

### **Tipos Y Variables**
- **gettype()** → devuelve el tipo.
- **is_array()** → comprueba si es array.
- **is_bool()** → comprueba si es booleano.
- **is_float()** → comprueba si es float.
- **is_integer()** → comprueba si es entero.
- **settype()** → cambia el tipo de una variable.
- **unset()** → elimina una variable.
- **isset()** → comprueba si existe y no es null.
- **empty()** → comprueba si está vacía.
- **is_null()** → comprueba si es null.

---

### **Constantes**
- **define()** → crea una constante.
- **const()** → crea una constante (versión del lenguaje).

---

### **Fechas Y Horas**
- **DateTime (clase)** → manejar fechas de forma avanzada.
- **date()** → formatea la fecha/hora actual.
- **date_default_timezone_set()** → cambia la zona horaria.
- **getdate()** → devuelve la fecha en array.

---

### **Inclusión De Archivos**
- **include** → incluye un archivo (si falla, aviso).
- **include_once** → igual pero solo una vez.
- **require** → incluye un archivo (si falla, error fatal).
- **require_once** → igual pero solo una vez.
- **function_exists()** → comprueba si una función existe.

---

### **Punteros De Arrays**
- **reset()** → mueve al primer elemento.
- **next()** → avanza uno.
- **prev()** → retrocede uno.
- **end()** → mueve al último elemento.
- **current()** → devuelve el valor actual.
- **key()** → devuelve la clave actual.

---

### **Manejo De Arrays**
- **array()** → crear un array.
- **unset()** → eliminar un índice.
- **array_values()** → devuelve solo los valores.
- **is_array()** → comprobar si es array.
- **count()** → contar elementos.
- **in_array()** → buscar si existe un valor.
- **array_search()** → devuelve la clave del valor.
- **array_key_exists()** → comprueba si existe una clave.

---

### **Otras Funciones**
- **highlight_file()** → muestra un archivo con colores.
- **show_source()** → igual que highlight_file().
- **setlocale()** → cambia la configuración regional.
- **strftime()** → formatea fecha según la locale.

---

### **PDO (Base de datos)**
- **PDO (clase)** → conexión a base de datos.
- **PDOStatement (clase)** → representa una sentencia preparada y sus resultados.
- **PDOException (clase)** → errores de PDO.
- **getAttribute()** → obtiene configuración del PDO.
- **setAttribute()** → cambia configuración del PDO.
- **unset()** → cerrar conexión eliminando el objeto.
- **exec()** → ejecutar SQL sin resultados (INSERT, UPDATE).
- **query()** → ejecutar SELECT directo.
- **fetch()** → obtener fila.
- **fetchObject()** → obtener fila como objeto.

#### **Transacciones**
- **beginTransaction()** → iniciar transacción.
- **commit()** → confirmar.
- **rollback()** → deshacer.

#### **Consultas preparadas**
- **prepare()** → preparar SQL.
- **bindParam()** → ligar parámetros.
- **execute()** → ejecutar sentencia.

---

### **JSON**
- **json_encode()** → convertir array/objeto a JSON.
- **json_decode()** → convertir JSON a array/objeto.

---

### **XML**
- **XMLReader** → lectura de XML paso a paso.
- **XMLWriter** → creación de XML.
- **SimpleXMLElement** → trabajar con XML de forma sencilla.

---

### **Cabeceras HTTP**
- **header()** → enviar cabeceras (redirecciones, tipo de contenido, etc.).

---

### **DOMDocument (Manipulación de XML/HTML)**
- **DOMDocument (clase)** → representa un documento XML/HTML y permite manipularlo.
