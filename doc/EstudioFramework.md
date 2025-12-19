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
    - [Primeros pasos (Preparar el entorno)](#primeros-pasos-preparar-el-entorno)
      - [Instalación](#instalación)
      - [Configuración](#configuración)
    - [Creación de un proyecto](#creación-de-un-proyecto)


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

### Primeros pasos (Preparar el entorno)

#### Instalación
#### Configuración

### Creación de un proyecto