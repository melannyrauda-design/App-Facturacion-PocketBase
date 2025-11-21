🚀 Sistema de Facturación y Gestión (SGF)

Una solución integral y moderna para la administración de PYMES, desarrollada como una Single Page Application (SPA). Este sistema unifica la facturación, el control financiero, la gestión de clientes y la productividad del equipo en una interfaz limpia y eficiente.

📋 Tabla de Contenidos

Características Principales

Tecnologías Utilizadas

Requisitos Previos

Instalación y Despliegue

Configuración del Backend (PocketBase)

Estructura del Proyecto

Contribución

✨ Características Principales

💰 Módulo de Ventas y Finanzas

Facturación y Recibos: Generación de documentos con cálculo automático de impuestos (ISV), descuentos y manejo de productos exentos/gravados.

Control de Correlativos: Gestión automática de rangos CAI y numeración de documentos.

Historial de Movimientos: Visor avanzado con filtros por fecha, cliente, tipo de documento y empresa.

Análisis de Morosidad: Reporte en tiempo real de cuentas por cobrar, clasificadas por antigüedad de la deuda (0-30, 30-60, 90+ días).

Estados de Cuenta: Generación de reportes detallados por cliente listos para imprimir.

📈 Productividad y Gestión (CRM)

Agenda Inteligente: Sistema de tareas tipo Kanban (Pendiente, En Curso, Completada).

Asignación de Tareas: Los administradores pueden asignar tareas a operadores y monitorear el progreso del equipo.

Notificaciones: Bandeja de entrada con alertas de tareas vencidas o por vencer.

Timer Pomodoro: Herramienta de enfoque integrada para maximizar la productividad.

🛡️ Seguridad y Administración

Roles y Permisos (RBAC): Sistema granular de permisos (Admin vs. Operador).

Gestión de Usuarios: Panel para crear, editar y administrar el acceso del personal.

Multi-Empresa: Soporte para gestionar la facturación de múltiples razones sociales.

🛠 Tecnologías Utilizadas

El proyecto sigue una arquitectura BaaS (Backend as a Service) para máxima eficiencia y portabilidad.

Frontend

HTML5 & JavaScript (ES6+): Lógica pura sin frameworks pesados (Vanilla JS).

Tailwind CSS (v3.4): Diseño responsivo y moderno cargado vía CDN.

SheetJS: Librería para la exportación de reportes a Excel (.xlsx).

Backend

PocketBase: Un backend open-source en un solo archivo ejecutable.

Base de datos SQLite embebida (tiempo real).

Autenticación de usuarios.

API RESTful automática.

📋 Requisitos Previos

Un navegador web moderno (Chrome, Edge, Firefox).

Conexión a internet (para cargar las librerías CDN de Tailwind y SheetJS).

PocketBase: El ejecutable del servidor backend.

🚀 Instalación y Despliegue

Paso 1: Configurar el Backend (PocketBase)

Descarga la última versión de PocketBase para tu sistema operativo.

Descomprime el archivo en una carpeta llamada backend dentro de tu proyecto.

Abre una terminal en esa carpeta y ejecuta:

./pocketbase serve


Accede al Admin UI en http://127.0.0.1:8090/_/ y crea tu cuenta de superusuario.

Paso 2: Configurar las Colecciones (Base de Datos)

Deberás recrear la estructura de datos en PocketBase. Las colecciones principales requeridas son:

users: (Sistema) Usuarios y contraseñas.

roles: Definición de roles (admin, operador) y permisos.

permissions: Catálogo de permisos (slugs como create_invoice, view_morosidad).

companies: Datos de tus empresas emisoras.

documents: Facturas y Recibos.

invoice_items: Detalle de productos en facturas.

clients y products: Maestros de datos.

agenda_tasks: Tareas y asignaciones.

Nota: Asegúrate de configurar las API Rules para permitir la lectura/escritura según el rol del usuario.

Paso 3: Ejecutar el Frontend

Clona este repositorio o descarga los archivos.

Abre el archivo index.html en tu navegador o sírvelo usando una extensión como "Live Server" en VS Code.

Asegúrate de que la URL de conexión en el script del index.html apunte a tu servidor local:

const pb = new PocketBase('[http://127.0.0.1:8090](http://127.0.0.1:8090)');


Inicia sesión con un usuario creado en el panel de PocketBase.

📂 Estructura del Proyecto

/
├── index.html          # El núcleo de la aplicación (HTML + JS + Lógica)
├── README.md           # Documentación del proyecto
└── /backend            # (Opcional) Carpeta sugerida para el ejecutable de PocketBase
    ├── pocketbase.exe
    └── pb_data/        # Aquí se guardará tu base de datos SQLite automáticamente


📄 Licencia

Este proyecto está bajo la Licencia MIT. No eres libre de usarlo, modificarlo y distribuirlo para fines personales o comerciales.

Desarrollado con ❤️ para optimizar la gestión empresarial.