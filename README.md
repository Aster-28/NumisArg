# NumisArg

NumisArg es una aplicación web para consultar monedas argentinas y organizar colecciones numismáticas. Permite explorar un catálogo con datos e imágenes de las monedas, crear una cuenta y guardar ejemplares en colecciones personales con su cantidad, estado y valor de mercado. Incluye además páginas de administración para gestionar datos del catálogo y usuarios.

## Tecnologías

- PHP
- MySQL o MariaDB
- Apache (por ejemplo, mediante XAMPP)
- HTML, CSS y JavaScript
- Tailwind CSS para los estilos

## Requisitos

- XAMPP u otro entorno con Apache, PHP y MySQL/MariaDB.
- Un navegador web.
- Node.js y npm solo si se va a trabajar con las dependencias de desarrollo de CSS.

## Instalación local con XAMPP

1. Copiá o cloná el proyecto en `C:\xampp\htdocs\numisarg`. El nombre `numisarg` es importante: el encabezado usa rutas absolutas con ese prefijo.
2. Iniciá Apache y MySQL desde el panel de XAMPP.
3. Abrí phpMyAdmin (`http://localhost/phpmyadmin`) y creá una base de datos llamada `numisarg`.
4. Seleccioná esa base e importá `base_de_datos/numisarg.sql`. El archivo crea las tablas y carga los datos de ejemplo; no crea la base de datos por sí solo.
5. Revisá `src/inc/conexion.php`. La configuración incluida espera MySQL en `localhost`, usuario `root`, contraseña vacía y base de datos `numisarg`. Si tu instalación usa otros datos, actualizalos allí.
6. Abrí `http://localhost/numisarg/` en el navegador.

## Funcionalidades

- Catálogo de monedas con búsqueda y consulta de detalles.
- Registro e inicio de sesión.
- Colecciones personales con monedas, cantidad, estado y valor de mercado.
- Gestión de perfil y cambio de contraseña.
- Sección administrativa para gestionar monedas, anomalías, divisas y usuarios.
- Formulario de contacto.

## Estructura del proyecto

```text
.
├── index.php                 # Página de inicio
├── header.php                # Navegación y sesión
├── footer.html               # Pie de página
├── base_de_datos/
│   └── numisarg.sql          # Esquema y datos de ejemplo
└── src/
    ├── inc/
    │   ├── conexion.php      # Conexión a MySQL
    │   └── PHPMailer/        # Código de envío de correo
    ├── js/                   # Funciones JavaScript
    ├── assets/               # Imágenes, iconos y otros recursos
    ├── php/                  # Acciones de sesión
    └── views/
        ├── admin-pages/      # Administración
        ├── coin-catalog/     # Catálogo y gestión de monedas guardadas
        ├── contact/          # Formulario de contacto
        ├── login/            # Registro, acceso y recuperación
        └── user-profile/     # Perfil y colecciones
```

## Estilos

El proyecto incluye los estilos utilizados por la aplicación y una configuración de Tailwind CSS. La dependencia de desarrollo se declara en `package.json`; se pueden instalar las dependencias con:

```bash
npm install
```

Actualmente `package.json` no define un comando de compilación ni de pruebas.

## Notas

- La conexión incluida en `src/inc/conexion.php` usa credenciales predeterminadas de desarrollo. Cambialas antes de desplegar la aplicación en un servidor.
- El formulario de contacto depende de la configuración SMTP de PHPMailer. Para habilitar el envío, revisá `src/views/contact/send_email.php` y configurá allí los datos del servidor de correo.
