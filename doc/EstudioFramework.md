# Estudio del framework Laravel

- [Estudio del framework Laravel](#estudio-del-framework-laravel)
  - [**Estudio teórico**](#estudio-teórico)
    - [Introducción](#introducción)
      - [¿Qué es?](#qué-es)
      - [¿Para qué sirve?](#para-qué-sirve)
    - [Características principales](#características-principales)
    - [Ventajas](#ventajas)
    - [Desventajas](#desventajas)
    - [Diferencias con PHP base (sin frameworks)](#diferencias-con-php-base-sin-frameworks)
    - [Estructura de directorios](#estructura-de-directorios)
    - [Referencias](#referencias)
  - [**Estudio practico**](#estudio-practico)
    - [Descripción del entrono](#descripción-del-entrono)
    - [Primeros pasos (Preparar el entorno)](#primeros-pasos-preparar-el-entorno)
      - [Instalación](#instalación)
        - [PHP](#php)
        - [Composer](#composer)
        - [Laravel](#laravel)
        - [NodeJS y npm](#nodejs-y-npm)
      - [Configuración](#configuración)
    - [Creación de un proyecto](#creación-de-un-proyecto)
    - [Configurar el proyecto](#configurar-el-proyecto)
    - [Artisan](#artisan)
    - [Como crear un primer proyecto simple](#como-crear-un-primer-proyecto-simple)
      - [Rutas](#rutas)
      - [Vistas](#vistas)
      - [Controladores](#controladores)
      - [Modelos](#modelos)
      - [Acceso a datos](#acceso-a-datos)
      - [Formularios y validaciones](#formularios-y-validaciones)
      - [Control de acceso](#control-de-acceso)
    - [Pasar la app a entorno explotación](#pasar-la-app-a-entorno-explotación)


## **Estudio teórico**

### Introducción

#### ¿Qué es?

Laravel es un framework de código abierto de PHP que da una estructura fija para crear aplicaciones web. \
En vez de que tú tengas que organizar todo desde cero, Laravel ya trae una forma de trabajar: carpetas ordenadas, archivos separados por función y muchas herramientas listas para usar.

#### ¿Para qué sirve?

Sirve para facilitar la creación de aplicaciones y paginas web de una forma mas rápida y estructurada. \
Ayuda especialmente en tareas típicas y que se repiten mucho en el desarrollo.

### Características principales

- Crea rutas para decidir qué hace la web cuando un usuario entra a una URL especifica.
- Usa el patrón de diseño **MVC (*Modelo-Vista-Controlador*)** para organizar los datos, lógica e interfaz.
- Gestión de la DB usando **Eloquent ORM** sin escribir SQL directamente.
- Gestión del control de acceso sin tener que programarlo de cero.
- Crear plantillas con **Blade** para reutilizar las vistas.
- Proteger la aplicación con sistemas ya integrados para ayudar a prevenir y protegerse de los ataques.

### Ventajas

- Fácil de aprender.
- Una gran comunidad activa.
- Código organizado y fácil de mantener.
- Trabajar con bases de datos de forma más sencilla y segura.
- Permite reutilizar código fácilmente con las plantillas.
- Seguridad integrada contra ataques comunes.

### Desventajas

- Requiere aprender su forma de trabajar con MVC, que puede ser complejo al principio.
- Para aplicaciones muy simples puede añadir complejidad innecesaria.
- Alguna actualización podría romper el código existente.

### Diferencias con PHP base (sin frameworks)

- Total control del código, sin estructura impuesta.
- Se debe programar todo desde cero, incluso tareas repetitivas.
- Mayor riesgo de errores de seguridad si no se tiene experiencia.
- No hay herramientas integradas para rutas, plantillas o bases de datos.

### Estructura de directorios

[Según la documentación oficial](https://laravel.com/docs/12.x/structure):
- `app/`: Contiene el código principal de la aplicación, incluyendo controladores, modelos, y lógica de negocio.
- `bootstrap/`: Incluye archivos para arrancar y configurar el framework.
- `config/`: Almacena todos los archivos de configuración de la aplicación, como la base de datos, caché y sesiones.
- `database/`: Contiene las migraciones, semillas y factorías de la base de datos.
- `public/`: Es el único directorio que debe ser accesible públicamente a través del servidor web. Contiene el archivo index.php y el resto de archivos de la aplicación.
- `resources/`: Contiene los recursos no compilados.
    - `lang/`: Para los textos del sitio en diferentes idiomas.
    - `views/`: Almacena las vistas de la aplicación (archivos Blade).
- `routes/`: Define las rutas de la aplicación en archivos como web.php y api.php.
- `storage/`: Contiene los archivos generados por la aplicación, como logs, caché de Blade y sesiones.
- `tests/`: Contiene los archivos para pruebas de unidad y de integración.
- `vendor/`: Contiene todas las dependencias del proyecto, gestionadas por Composer.

### Referencias

Tutorial oficial: https://laravel.com/learn/getting-started-with-laravel

Documentación oficial: https://laravel.com/docs/12.x

Curso Laravel YouTube: https://www.youtube.com/playlist?list=PLZ2ovOgdI-kVtF2yQ2kiZetWWTmOQoUSG



## **Estudio practico**

### Descripción del entrono

* **Sistema operativo local:** Windows 10 - *Usado para el desarrollo por la facilidad de uso.*
* **Sistema operativo explotación:** Ubuntu Server - *Usado en producción por estabilidad y seguridad.*
* **Servidor web local:** Artisan - *Permite ejecutar y probar la aplicación rápidamente en desarrollo.*
* **Servidor web explotación:** Apache - *Sirve la aplicación de forma estable en producción.*
* **PHP:** 8.3 - *Usamos esta versión porque es compatible con la ultima versión de Laravel (12) y es la ultima disponible en el servidor de explotación.*
* **Gestor de dependencias:** Composer - *Permite instalar y gestionar las librerías necesarias del proyecto de forma sencilla.*
* **Base de datos:** MariaDB - *Sistema de gestión de bases de datos relacional, con entornos separados para pruebas y producción.*
* **Framework:** Laravel - *Framework PHP que facilita la estructura, seguridad y mantenimiento de la aplicación.*
* **Gestión de versiones:** Git y GitHub - *Permite llevar un control de cambios del código y colaboración entre desarrolladores.*
* **Editor:** VS Code - *Entorno de desarrollo ligero y configurable, con soporte para PHP y Laravel.*
* **Navegador:** Chrome y Firefox - *Usados para probar y depurar la aplicación, garantizando compatibilidad entre navegadores.*

### Primeros pasos (Preparar el entorno)

#### Instalación

Para usar Laravel tenemos que instalar PHP, Composer, el propio Laravel para poder crear la aplicación y NodeJS y npm para compilar los archivos del frontend.

##### PHP

Abrimos una terminal y ponemos:
```powershell
winget install PHP.PHP.8.3 # Para el usuario actual
# o
winget install PHP.PHP.8.3 --scope machine # Para todos los usuarios
```

Esto instalara PHP 8.3 automáticamente y lo añadirá a PATH (hay que reiniciar la terminal para que haga efecto). \
Puedes comprobar que es la versión correcta con `php -v`

Después, lo [configuramos](#configuración).

##### Composer

Vamos a https://getcomposer.org/download/ y, descargamos y ejecutamos "***Composer-Setup.exe***".

Le damos a instalar para todos o solo este usuario según queramos. En las opciones de instalación le damos a siguiente hasta instalar.

##### Laravel

Abrimos una nueva terminal para recargar los PATH, y ponemos:
```powershell
composer global require laravel/installer
```

Esto instalara Laravel y todas sus dependencias.

##### NodeJS y npm

Vamos a https://nodejs.org/es/download y abajo, le damos al botón para descargar el `.msi`.

Lo ejecutamos, le damos a siguiente, aceptamos la licencia, y le damos a siguiente hasta instalar.

Podemos comprobar que funciona haciendo `node -v` y `npm -v` respectivamente.

#### Configuración

Para ver donde esta y configurar el archivo de php.ini podemos usar:
```powershell
(Get-Command php).Source
```

Por defecto el archivo tiene dos php.ini: `php.ini-development` y `php.ini-production`.

El de desarrollo lo copiamos y lo pegamos como `php.ini`, al final de todo el archivo ponemos:
```ini
extension_dir = "ext"
extension=curl
extension=fileinfo
extension=mbstring
extension=openssl
extension=pdo_mysql
```

### Creación de un proyecto

Para crear un proyecto, se haría por terminal haciendo algo tipo:
```
C:\...\proyectos> laravel new nombre_proyecto
```
Nos preguntara ***( yo he seleccionado )***:
1. Que kit de inicio queremos usar. ***( El predeterminado: none )***
2. Que framework para test preferimos. ***( El predeterminado: Pest )***
3. Si queremos instalar "Laravel Boost" para programación con IA. ***( No )***
4. *... [Se instalaran un montón de paquetes y dependencias] ...*
5. Que base de datos usaremos. ***( mariadb )***
6. Si queremos hacer las migraciones por defecto a la DB. ***( El predeterminado: yes )***
7. *... [Se instalaran todavía mas paquetes y dependencias] ...*
8. Si queremos hacer `npm install` y `npm run build`. ***( El predeterminado: yes )***

Al terminar creara una carpeta con el nombre del proyecto que contenga todos los archivos y directorio iniciales.

Hacemos:
```bash
cd nombre_proyecto  # Para ir al proyecto
composer run dev    # Para iniciar el servidor web
```

Ahora, si vamos a http://localhost:8000/ podremos ver esta pagina:
![imagen pagina inicio app por defecto](img/homePageDefaultApp.png)

### Configurar el proyecto

Para configurar el proyecto están el archivo `.env` que hay el la raíz del proyecto y los archivos de la carpeta `/config`.

El `.env` es el archivo de config principal. Ahí podemos configurar varias cosas. *(Los mas importantes siendo el **nombre de la aplicación**, el **entorno de desarrollo**, la **clave para encriptar datos**, si mostraremos **mensajes de error** en la app, la **url de la app** y la **DB que usaremos con su usuario y contraseña**)*

Para configurar la zona horaria, en la carpeta `/config` el archivo `app.php` buscamos "***timezone***", y lo ponemos en "***Europe/Madrid***".

### Artisan

Artisan es la interfaz de línea de comandos de Laravel. Es la herramienta principal para automatizar tareas comunes, desde **iniciar un servidor** hasta **generar código** y **gestionar la base de datos**.

Algunas de las cosas mas útiles que puedes hacer con Artisan son:

Iniciar un servidor web:
```bash
php artisan serve
```
La aplicación será accesible desde http://localhost:8000.

Generar código automáticamente:
```bash
php artisan make:<tipo> <Nombre>
# Ejemplo: php artisan make:controller UsuarioController
```

Crear las tablas de la DB con:
```bash
php artisan migrate
```

Puedes ver todas las opciones que tiene usando:
```bash
php artisan list
```

### Como crear un primer proyecto simple

#### Rutas
En Laravel, las rutas son la forma de definir cómo tu aplicación responde a una solicitud HTTP específica. Se definen en los archivos de la carpeta `routes/`. \
El archivo `web.php` es donde se guardan las rutas para la web.

Ejemplo:
```php
use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return view('welcome'); // Muestra la vista 'welcome.blade.php'
});
Route::get('/perfil', function () {
    $nombre = "Jesús";
    return view('perfil', ['nombre' => $nombre]); // Pasa la variable $nombre a la vista
});

Route::get('/hola', function () {
    return '¡Hola Mundo!'; // Devuelve un texto plano
});

Route::get('/login', [UsuarioController::class, 'mostrarLogin']); // Llama al metodo mostrarLogin del controlador del usuario al hacer GET
Route::post('/login', [UsuarioController::class, 'login']); // La misma ruta llama al metodo login del controlador del usuario al hacer POSR

Route::get(...) // Responde a peticiones GET
Route::post(...) // Responde a peticiones POST
Route::put(...) // Responde a peticiones PUT
// etc
```

#### Vistas
En Laravel, las vistas son los archivos que contienen el HTML de tu aplicación. Normalmente se encuentran en la carpeta `resources/views`.

Laravel utiliza Blade, su motor de plantillas, que permite usar plantillas dinámicas y directivas como **@if/@else**, **@foreach**, **@include**, etc. \
También se le pueden pasar datos a la vista desde la ruta o el controlador.

Ejemplo siguiendo la ruta '/perfil' del ejemplo de rutas:
```php
<!DOCTYPE html>
<html>
<head>
    <title>Perfil de usuario</title>
</head>
<body>
    <h1>Perfil</h1>
    <p>Hola, {{ $nombre }}!</p> <!-- Muestra la variable pasada desde la ruta -->
</body>
</html>
```

#### Controladores
En Laravel, los controladores se usan para organizar la lógica de las rutas y no tener todo el código dentro de `web.php`. \
Se crean normalmente en la carpeta `app/Http/Controllers`.

Podemos crear un controlador usando ``php artisan make:controller UsuarioController``.

Ejemplo:
```php
namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Models\Usuario; // Modelo para acceder a la base de datos

class UsuarioController extends Controller
{
    // Muestra el formulario de login
    public function mostrarLogin() {
        return view('login');
    }

    // Procesar login
    public function login(Request $request) {
        $email = $request->input('email');
        $password = $request->input('password');

        // Ejemplo sencillo de búsqueda en la base de datos
        $usuario = Usuario::where('email', $email)
                          ->where('password', $password) // esto no es seguro, solo ejemplo
                          ->first();

        if ($usuario) {
            return view('perfil', ['nombre' => $usuario->nombre]);
        } else {
            return back()->with('error', 'Credenciales incorrectas');
        }
    }

    // Otro método de ejemplo para listar usuarios
    public function listar() {
        $usuarios = Usuario::all(); // Trae todos los usuarios
        return view('usuarios', ['usuarios' => $usuarios]);
    }
}
```

#### Modelos
En Laravel, los modelos representan las tablas de la base de datos y nos permiten interactuar con ellas de manera sencilla usando Eloquent, el ORM de Laravel. \
Se crean normalmente en la carpeta `app/Models`.

Podemos crear un modelo usando ``php artisan make:model Usuario``.

Ejemplo:
```php
namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Usuario extends Model
{
    use HasFactory;

    // Nombre de la tabla (opcional si no sigue la convención plural)
    protected $table = 'usuarios';

    // Campos que se pueden asignar en masa
    protected $fillable = ['nombre', 'email', 'password'];

    // Campos ocultos al convertir a JSON o array
    protected $hidden = ['password'];

    // Los casts permiten convertir automáticamente los atributos al tipo deseado al guardar o leer datos
    protected function casts(): array {
        return [ 'password' => 'hashed', ];
    }
}
```

#### Acceso a datos
En Laravel, podemos acceder a la base de datos de varias formas usando Eloquent (ORM) o el Query Builder. \
Se recomienda usar normalmente EloquentORM a no ser que necesites hacer cosas muy especificas

Ejemplo Eloquent:
```php
use App\Models\Usuario;

// Crear un usuario
Usuario::create([
    'nombre' => 'Jesús',
    'email' => 'jesus@example.com',
    'password' => '1234', // Laravel lo hashea automáticamente por el cast() del modelo
]);

// Obtener un usuario por email
$usuario = Usuario::where('email', 'jesus@example.com')->first();

// Actualizar un usuario
$usuario->nombre = 'Jesús';
$usuario->save();

// Eliminar un usuario
$usuario->delete();

// Obtener todos los usuarios
$usuarios = Usuario::all();
```

Ejemplo Query Builder:
```php
use Illuminate\Support\Facades\DB;

// Insertar un usuario
DB::table('usuarios')->insert([
    'nombre' => 'Ana',
    'email' => 'ana@example.com',
    'password' => bcrypt('1234'), // Hash manual
]);

// Obtener usuarios
$usuarios = DB::table('usuarios')->get();

// Actualizar
DB::table('usuarios')
    ->where('email', 'ana@example.com')
    ->update(['nombre' => 'Ana Pérez']);

// Eliminar
DB::table('usuarios')
    ->where('email', 'ana@example.com')
    ->delete();
```

#### Formularios y validaciones
En Laravel, los formularios se usan para enviar datos desde una vista al servidor, normalmente mediante métodos POST. \
Las validaciones permiten comprobar que los datos recibidos son correctos antes de procesarlos o guardarlos en la base de datos.

Laravel facilita esto usando el objeto **`Request`** y el método **`validate()`**.

Ejemplo (formulario):
```php
<form action="/login" method="POST">
    @csrf <!-- Protección contra ataques CSRF. Es obligarorio ponerlo en todas las peticiones que no son get -->
    // @method('PUT') <!-- Podemos especificar otro método HTTP si queremos -->

    <label>Email:</label>
    <input type="email" name="email">

    <label>Contraseña:</label>
    <input type="password" name="password">

    <button type="submit">Entrar</button>
</form>
```

Ejemplo (validación en en controlador):
```php
public function login(Request $request)
{
    $request->validate([
        'email' => ['required', 'email', Rule::unique("users", "email")], // El email es obligatorio, debe ser un email válido y único en la tabla users
        'password' => ['required', 'min:4', 'max:22'], // La contraseña es obligatoria, con longitud entre 4 y 22 caracteres
    ]);

    // Si la validación pasa, el código continúa. Si falla, Laravel vuelve al formulario con errores.
    return 'Datos válidos';
}
```

#### Control de acceso
Laravel gestiona el control de acceso de usuarios mediante el sistema de autenticación **`auth()`**. \
Este sistema permite iniciar sesión, cerrar sesión y acceder a la información del usuario autenticado.

Ejemplo (iniciar sesión):
```php
$esUsuarioValido
 = auth()->guard()->attempt([ // Si es correcto, tambien crea la sesión del usuario.
    'name' => $camposRecibidos['nombrelogin'],
    'password' => $camposRecibidos['contraseñalogin']
]);

if ($esUsuarioValido) {
    // Inicio de sesión exitoso
    return redirect('/dashboard');
} else {
    // Credenciales incorrectas
    return redirect("login")->withErrors(['login' => 'Credenciales incorrectas']);
}
```

Ejemplo (cerrar sesión):
```php
auth()->guard()->logout(); // Cierra la sesión del usuario
return redirect('/'); // Redirige a la página principal
```

Ejemplo (obtener usuario autenticado):
```php
$usuario = auth()->guard()->user(); // Obtiene el usuario autenticado
echo $usuario->name; // Muestra el nombre del usuario
echo $usuario->email; // Muestra el email del usuario
// etc
```

#### Migraciones
En Laravel, las migraciones sirven para crear y modificar la estructura de la base de datos de forma controlada y versionada, sin escribir SQL directamente. \
Se crean en la carpeta `database/migrations`.

Podemos crear una usando `php artisan make:migration create_usuarios_table`.

Ejemplo (definir la estructura de una tabla):
```php
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    // Se ejecuta al aplicar la migración. Crea la tabla 'usuarios'.
    public function up(): void
    {
        Schema::create('usuarios', function (Blueprint $table) {
            $table->id(); // ID autoincremental
            $table->string('nombre');
            $table->string('email')->unique();
            $table->string('password');
            $table->timestamps(); // Crea automáticamente las columnas 'created_at' y 'updated_at'
            $table->string('nombre_completo')->nullable(); // Campo opcional

            // Clave foránea hacia roles:
            // - rol_usuario → columna de ESTA tabla (usuarios)
            // - id_rol → columna de la OTRA tabla (roles)
            $table->foreignId('rol_usuario')
                  ->constrained('roles', 'id_rol') // Si la columna se llamara 'id' en vez de 'id_rol' bastaría con ->constrained('roles')
                  ->onDelete('cascade'); // si se borra un rol, se borran los usuarios asociados
        });
    }

    // Se ejecuta al revertir la migración. Elimina la tabla 'usuarios'.
    public function down()
    {
        Schema::dropIfExists('usuarios'); // Elimina la tabla si existe
    }
}
```

Una vez definidas las migraciones, podemos aplicarlas a la base de datos con:
```bash
php artisan migrate # Crea las tablas definidas en las migraciones
php artisan migrate:rollback # Revierte la última migración aplicada
php artisan migrate:fresh # Elimina todas las tablas y vuelve a crear todo desde cero
```

### Pasar la app a entorno explotación

Primero en el `.env` cambiamos esto:
```ini
APP_NAME=Laravel
APP_ENV=local
APP_DEBUG=true
APP_URL=http://localhost:8000
```
Por esto:
```ini
APP_NAME=Laravel
APP_ENV=production
APP_DEBUG=false
APP_URL=https://jesustemgal.ieslossauces.es/proyectoLaravel
```
*(Además de los datos de la conexión a la DB)*

Después tenemos que subir la aplicación a GitHub si no lo habíamos hecho ya.

Una vez este en un repositorio, podemos ir a nuestro Plex y creamos un subdominio y una DB asociada a el *(y ponemos los datos en el `.env`)*. \
Después en la barra lateral de la izquierda entramos en el apartado "***Laravel***", le damos a instalar aplicación y seleccionamos el subdominio, elegimos instalar desde repo remoto, ponemos la url al repo y le damos a instalar aplicación.

Una vez hecho esto, en el panel para Laravel que se nos abre; en la config le damos a edita `.env` y pegamos el nuestro de explotación, en el apartado de artisan hacemos un `migrate` para que se creen las tablas de la DB automáticamente y luego en el apartado de despliegue le damos a ***desplegar***. Si ahora vamos a la url del subdominio ya debería de funcionar.

[**-> Link a la aplicación en explotación <-**](https://laravel.jesustemgal.ieslossauces.es/) \
[**-> Link a su repositorio <-**](https://github.com/yatusabebeibe/proyectoLaravel/)