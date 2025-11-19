# InvoiceManager - Sistema de Gestión de Facturas (Portfolio Showcase)

InvoiceManager es una aplicación web para visualizar y gestionar facturas de manera centralizada. Este proyecto fue desarrollado durante una pasantía y, debido a políticas de confidencialidad, el código fuente no es público.

## Visión General del Proyecto

InvoiceManager funciona como la interfaz de usuario (frontend) para un sistema de gestión de facturas más amplio. Su propósito es permitir a los usuarios autenticados acceder, buscar y analizar la información de las facturas de su empresa, que es procesada y almacenada por un servicio de backend.

**Componentes Clave:**

1.  **Servicio de Backend (MailProcessor):** Un servicio encargado de conectarse a una cuenta de correo, extraer automáticamente la información de facturas (archivos PDF y JSON) y guardarla en una base de datos PostgreSQL.
2.  **InvoiceManager (Frontend):** Esta aplicación, que consume los datos de esa misma base de datos para ofrecer una interfaz de usuario funcional y rica en características.

Ambos componentes interactúan a través de una base de datos PostgreSQL compartida, lo que permite una gestión eficiente y escalable de los datos de las facturas.

## Demo
![Imagen 1](/demo1.gif)
## Características Destacadas

*   **Autenticación Segura:** Implementación de un sistema de autenticación robusto para proteger el acceso a la información sensible de las facturas.
*   **Visualización Interactiva de Facturas:** Interfaz intuitiva para explorar y gestionar facturas.
*   **Búsqueda y Filtrado Avanzado:** Funcionalidades para buscar y filtrar facturas eficientemente.
*   **Análisis de Datos:** Integración de gráficos para visualizar tendencias y métricas clave de las facturas.
*   **Gestión de Empresas:** Módulos dedicados para la administración de información de empresas asociadas a las facturas.

## Stack Tecnológico

-   **Framework:** [Next.js](https://nextjs.js.org/)
-   **Lenguaje:** [TypeScript](https://www.typescriptlang.org/)
-   **Base de Datos:** [PostgreSQL](https://www.postgresql.org/) (interacción a través del backend)
-   **Autenticación:** [NextAuth.js](https://next-auth.js.org/)
-   **Estilos:** [Tailwind CSS](https://tailwindcss.com/) y [DaisyUI](https://daisyui.com/)
-   **Validación de Datos:** [Zod](https://zod.dev/)
-   **Visualización de Datos:** [ECharts for React](https://github.com/hustcc/echarts-for-react)

## Configuración para Desarrollo Local (Referencia)

Para aquellos interesados en el entorno de desarrollo, estos son los requisitos y pasos generales:

### Requerimientos

-   [Node.js](https://nodejs.org/)
-   [pnpm](https://pnpm.io/)
-   [PostgreSQL](https://www.postgresql.org/) Base de datos en ejecución (para el sistema completo).

### Instalación y Ejecución

1.  **Instalar dependencias:**
    ```bash
    pnpm install
    ```

2.  **Configurar variables de entorno:**
    Se requiere un archivo `.env` con variables como `POSTGRES_URL` y `AUTH_SECRET` para la conexión a la base de datos y la autenticación.

3.  **Ejecutar la Aplicación:**
    ```bash
    pnpm dev
    ```
    La aplicación estará disponible en `http://localhost:3000`.

## Estructura del Proyecto

-   **/app:** Contiene las rutas, páginas y layouts de la aplicación, siguiendo la convención del App Router de Next.js.
    -   **/app/api:** Rutas de API.
    -   **/app/companies:** Páginas para la gestión de empresas.
    -   **/app/dashboard:** Componentes y lógica de la página del panel de control.
    -   **/app/invoices:** Páginas para la gestión de facturas.
-   **/app/lib:** Lógica, acciones de servidor, definiciones de tipos y conexión a la base de datos.
-   **/app/ui:** Componentes de React reutilizables (botones, formularios, etc.).
-   **/auth:** Configuración de la autenticación con NextAuth.js.
