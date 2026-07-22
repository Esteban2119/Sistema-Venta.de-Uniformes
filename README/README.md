# Sistema de Venta de Uniformes

## Descripción del Proyecto

Para el desarrollo del Sistema de Venta de Uniformes se decidió implementar una arquitectura moderna, organizada y escalable que facilite el mantenimiento del software y permita su crecimiento futuro. La aplicación estará compuesta por un cliente (Frontend), un servidor (Backend) y una base de datos, comunicándose mediante una API REST.

Esta arquitectura permite separar claramente las responsabilidades de cada componente, haciendo que el sistema sea más fácil de desarrollar, mantener y ampliar.

---

## Tipo de arquitectura: 
    Cliente-Servidor con Arquitectura por Capas.

El sistema utiliza una combinación de:

- **Arquitectura Cliente - Servidor**
- **Arquitectura por Capas**

Ambas trabajan juntas para lograr una aplicación organizada, segura y fácil de mantener.

---

## Arquitectura Cliente - Servidor

Esta arquitectura separa la aplicación en un **cliente**, encargado de la interfaz de usuario, y un **servidor**, encargado de procesar la información y la lógica del sistema.


Frontend
(React + TypeScript)
        │
        ▼
Backend
(Node.js + Express + TypeScript)
        │
        ▼
Base de Datos
(PostgreSQL)


Porque permite:

Separar la interfaz del usuario y la lógica del negocio.
Mejorar la seguridad al evitar acceso directo a la base de datos.
Facilitar el mantenimiento y crecimiento del sistema.
Reutilizar la API para futuras aplicaciones móviles.

---

## Arquitectura por Capas

El backend utiliza una arquitectura por capas, donde cada parte del sistema tiene una responsabilidad específica.

Presentación
      ↓
Lógica del Negocio
      ↓
Acceso a Datos
      ↓
Base de Datos

Capas principales:
Presentación: Interfaz desarrollada en React, TypeScript y CSS.
Lógica del Negocio: Backend con Node.js, Express y TypeScript encargado de procesos, validaciones y autenticación JWT.
Acceso a Datos: Comunicación con PostgreSQL mediante consultas y operaciones CRUD.
Base de Datos: Almacenamiento de la información del sistema.
¿Por qué se eligió?

Porque permite:

Organizar mejor el código.
Separar responsabilidades.
Facilitar el mantenimiento y escalabilidad.
Agregar nuevos módulos de forma más sencilla.

---

## Arquitectura Cliente - Servidor

# Arquitectura del Sistema

El proyecto está dividido en tres partes principales:

```
SistemaVentaUniformes/

│
├── frontend/     → Interfaz de usuario (React + TypeScript + CSS)
│
├── backend/      → API REST y lógica del negocio (Node.js + Express + TypeScript)
│
├── database/     → Scripts y configuración de base de datos
│
├── docs/         → Documentación del proyecto
│
├── README.md     → Información general del sistema
│
├── LICENSE       → Licencia del proyecto
│
└── .gitignore    → Archivos excluidos del repositorio
```

---

# Frontend

## Tecnologías

* React
* TypeScript
* CSS
* Axios (consumo de API REST)

El frontend es responsable de la interfaz gráfica, interacción con el usuario y comunicación con el backend.

## Arquitectura de carpetas

```
frontend/
│
└── src/
    │
    ├── assets/       → Imágenes, iconos y recursos estáticos
    │
    ├── components/   → Componentes reutilizables de la interfaz
    │
    ├── layouts/      → Estructuras generales de páginas
    │
    ├── pages/        → Vistas principales del sistema
    │
    ├── routes/       → Configuración de navegación y rutas
    │
    ├── services/     → Comunicación con la API del backend
    │
    ├── hooks/        → Hooks personalizados de React
    │
    ├── context/      → Manejo del estado global
    │
    ├── styles/       → Archivos de estilos CSS
    │
    ├── types/        → Definición de tipos TypeScript
    │
    ├── utils/        → Funciones auxiliares
    │
    ├── App.tsx       → Componente principal
    │
    └── main.tsx      → Punto de entrada de la aplicación
```

---

# Backend

## Tecnologías

* Node.js
* Express
* TypeScript
* JWT para autenticación
* API REST

El backend contiene la lógica del negocio, gestión de usuarios, autenticación, validaciones y comunicación con la base de datos.

Utiliza una arquitectura modular basada en capas para mantener un código organizado y escalable.

## Arquitectura de carpetas

```
backend/
│
└── src/
    │
    ├── config/          → Configuraciones generales del sistema
    │
    ├── controllers/     → Controladores que reciben y responden solicitudes HTTP
    │
    ├── routes/          → Definición de endpoints de la API REST
    │
    ├── middlewares/     → Validaciones, seguridad y autenticación JWT
    │
    ├── services/        → Lógica del negocio
    │
    ├── repositories/    → Acceso y consultas a la base de datos
    │
    ├── models/          → Modelos de datos
    │
    ├── database/        → Configuración de conexión a la base de datos
    │
    ├── interfaces/      → Interfaces de TypeScript
    │
    ├── types/           → Tipos personalizados
    │
    ├── utils/           → Funciones generales reutilizables
    │
    ├── app.ts           → Configuración de Express
    
```

---

# Comunicación entre Frontend y Backend

La comunicación del sistema funciona mediante una API REST:

```
Usuario
  │
  ▼
Frontend
(React + TypeScript)
  │
  │ HTTP Requests
  │
  ▼
Backend
(Node.js + Express)
  │
  │
  ▼
Base de Datos
```

El frontend realiza solicitudes al backend mediante endpoints protegidos, mientras que el backend procesa la información, valida permisos y devuelve respuestas en formato JSON.

---

# Autenticación

El sistema utiliza autenticación mediante **JWT (JSON Web Token)**.

Flujo:

1. El usuario inicia sesión.
2. El backend valida las credenciales.
3. Se genera un token JWT.
4. El frontend almacena el token.
5. Las solicitudes protegidas envían el token para validar acceso.

---

# Base de Datos

La carpeta:

```
database/
```

contiene los scripts, configuraciones y recursos necesarios para la administración de la base de datos del sistema.

---

# Documentación

La carpeta:

```
docs/
```

contiene documentos relacionados con:

* Diagramas UML
* Diseño del sistema
* Arquitectura
* Manuales técnicos

---

# Instalación del Proyecto

## Backend

```bash
cd backend
npm install
npm run dev
```

## Frontend

```bash
cd frontend
npm install
npm run dev
```

---

# Objetivo de la Arquitectura

La arquitectura implementada busca:

* Separar responsabilidades.
* Facilitar mantenimiento del código.
* Mejorar la escalabilidad.
* Permitir futuras ampliaciones del sistema.
* Mantener una estructura profesional basada en buenas prácticas de desarrollo.
