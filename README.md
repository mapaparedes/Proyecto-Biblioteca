# Sistema de Gestión de Biblioteca (SGB) - Duoc UC 

Este repositorio contiene el desarrollo del **Sistema de Gestión de Biblioteca (SGB)**, un proyecto de software diseñado para modernizar y automatizar los flujos de circulación, control de inventario y gestión de usuarios de una biblioteca universitaria, reemplazando el registro manual tradicional

El proyecto está estructurado utilizando buenas prácticas de ingeniería de software, siguiendo el estándar **IEEE 830** para la especificación de requisitos y la metodología **RUP** para el ciclo de vida iterativo.

---

##  Tecnologías y Entorno Operativo
* **Backend:** Java (Versión 17 o superior) con el framework **Spring Boot**.
* **Frontend:** HTML5, CSS3 y JavaScript vanilla para una interfaz web intuitiva y ligera.
* **Base de Datos:** **MySQL** (Relacional, con soporte para cifrado de datos en reposo).
* **Integración de Hardware:** Módulos compatibles con escáneres ópticos USB para la lectura de códigos de barras (ISBN y credenciales).

---

## Diseño y Arquitectura (Modelo 4+1)
El sistema implementa una arquitectura cliente-servidor robusta desacoplada en tres capas principales:
1. **Capa de Presentación:** Interfaz web adaptada al perfil del usuario (CAPO para alumnos/docentes y panel técnico para bibliotecarios).
2. **Capa Lógica de Negocio:** Validación estricta de políticas (máximo 5 libros simultáneos, cálculo automático de fechas de vencimiento y multas).
3. **Capa de Acceso a Datos:** Conexión segura e integridad referencial centralizada en la base de datos.

*Nota: El sistema soporta operaciones paralelas asíncronas, permitiendo búsquedas en el catálogo mientras el personal procesa devoluciones simultáneamente.*

---

##  Requisitos Críticos Implementados (Matriz ERS)
El desarrollo prioriza los casos de uso transaccionales de alto riesgo del documento de requisitos:

* **RF-04 (Inicio de Sesión):** Autenticación segura mediante control de accesos basado en roles (RBAC).
* **RF-08 (Búsqueda de Libros):** Motor de búsqueda CAPO por título, autor o ISBN con respuesta menor a 3 segundos.
* **RF-10 (Registro de Préstamos):** Automatización de salida mediante el escaneo consecutivo del carnet de usuario y el código de barras del ejemplar.
* **RF-11 (Registro de Devoluciones):** Actualización instantánea del estado físico a "Disponible" y auditoría de alertas de morosidad.

---

## Equipo de Trabajo 
El proyecto está gestionado por un equipo multidisciplinario con responsabilidades asignadas en el tablero Kanban

* **Zachary Bazile** - Product Owner (Supervisión y Planificación Inicial)
* **Ignacio Miranda** - Arquitecto / Diseñador de Software (Modelado UML y Base de Datos)
* **Jordan Caro** - Analista de Sistemas (Levantamiento de Requisitos y Validación ERS)
* **Alejandro Romero** - Desarrollo Full-Stack (Implementación de Frontend y Backend)
* **Milton Paredes A.** - Científico de Datos (Módulo de Reportes, Estadísticas Avanzadas e Inventario)
* **Equipo QA** - Pruebas de Calidad Final y Validación Funcional.

---

##  Estructura del Repositorio
```text
SGB-Biblioteca/
├── backend/               # API REST construida con Spring Boot
├── frontend/              # Vistas web (Catálogo CAPO y Panel Técnico)
├── database/              # Scripts SQL para el esquema relacional de MySQL
├── docs/                  # Documento ERS (IEEE 830) y diagramas de arquitectura
└── README.md              # Este archivo informativo
