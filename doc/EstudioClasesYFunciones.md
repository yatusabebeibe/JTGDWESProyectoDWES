# **Estudio clases y funciones**

- [**Estudio clases y funciones**](#estudio-clases-y-funciones)
  - [**Mas importantes**](#mas-importantes)
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
