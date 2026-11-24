# Arquitectura técnica — Notes Manager

## 1. Stack tecnológico

| Componente | Tecnología |
|---|---|
| Runtime local | Node.js 26.13.1 |
| Runtime de despliegue | Node.js 26.x |
| Gestor de paquetes | npm 11.20.0 (local) |
| Framework | Next.js — App Router |
| Lenguaje | TypeScript |
| Interfaz | React |
| Estilos | Tailwind CSS |
| Validación | Zod |
| Base de datos | Firebase Cloud Firestore |
| Acceso a datos | Firebase Admin SDK |
| Pruebas unitarias | Vitest |
| Pruebas funcionales | Playwright |
| Análisis estático | ESLint |
| Despliegue | Vercel |

Las versiones exactas de las dependencias deberán definirse antes de implementar y ser idénticas para ambos proyectos.

## 2. Arquitectura

Se utilizará una aplicación full stack con Next.js.

La arquitectura estará organizada en tres responsabilidades:

- Presentación: componentes React e interfaz de usuario.
- Backend: API REST mediante Next.js Route Handlers.
- Persistencia: acceso a Cloud Firestore mediante Firebase Admin SDK.

La interfaz se comunicará con el backend mediante HTTP y JSON.

El acceso a Firestore se realizará exclusivamente desde el servidor.

No se utilizarán microservicios ni frameworks adicionales de backend.

## 3. Contratos REST

| Método | Endpoint | Operación | Requisito |
|---|---|---|---|
| POST | /api/notes | Crear nota | RF-01 |
| GET | /api/notes | Listar notas | RF-02 |
| GET | /api/notes/{id} | Consultar nota | RF-03 |
| PUT | /api/notes/{id} | Editar nota | RF-04 |
| DELETE | /api/notes/{id} | Eliminar nota | RF-05 |
| GET | /api/notes?q=value | Buscar notas | RF-06 |
| GET | /api/notes?category=value&status=value | Filtrar notas | RF-07 |
| PATCH | /api/notes/{id}/status | Archivar o restaurar | RF-08, RF-09 |

La búsqueda y los filtros podrán combinarse mediante parámetros de consulta.

### Códigos HTTP

| Código | Descripción |
|---|---|
| 200 | Operación satisfactoria |
| 201 | Recurso creado |
| 204 | Recurso eliminado |
| 400 | Solicitud inválida |
| 401 | Acceso no autorizado |
| 404 | Recurso no encontrado |
| 500 | Error interno |

Las fechas se representarán en formato ISO 8601 en las respuestas JSON.

## 4. Persistencia

Se utilizará una colección denominada `notes` en Cloud Firestore.

El identificador del documento será el identificador de la nota.

Los campos deberán corresponder al modelo definido en `docs/specification.md`.

Las fechas se almacenarán mediante el tipo Timestamp de Firestore.

Para el volumen reducido de esta POC, la búsqueda parcial por título y contenido podrá realizarse en el backend, sin incorporar motores externos de búsqueda.

## 5. Configuración

Las credenciales de Firebase se gestionarán mediante variables de entorno:

- `FIREBASE_PROJECT_ID`
- `FIREBASE_CLIENT_EMAIL`
- `FIREBASE_PRIVATE_KEY`

Se utilizará:

- `.env.local`: configuración local.
- `.env.example`: plantilla sin credenciales.
- Variables de entorno de Vercel: configuración del despliegue.

Las credenciales estarán disponibles únicamente en el servidor.

Antes del despliegue se deberá aprobar un mecanismo mínimo de protección de acceso, sin incorporar un sistema completo de gestión de usuarios.

## 6. Infraestructura

| Servicio | Plan |
|---|---|
| Firebase | Spark |
| Vercel | Hobby |

Cada implementación utilizará su propio proyecto Firebase y Vercel, evitando compartir datos o configuraciones.

Se aplicarán las restricciones presupuestarias establecidas en `docs/constitution.md`.

## 7. Estrategia de pruebas

- Vitest: validaciones, reglas de negocio y lógica de procesamiento.
- Playwright: flujos funcionales desde la interfaz web.
- Firestore: pruebas de persistencia con datos ficticios y aislados.
- TypeScript: verificación de tipos.
- ESLint: análisis estático.
- Next.js: compilación de producción.

Los criterios funcionales de validación estarán definidos en `docs/acceptance.md`.

## 8. Estructura del proyecto

El agente deberá proponer la estructura del código fuente durante la fase PLAN, respetando las convenciones de Next.js y conservando los documentos existentes.

La aplicación deberá inicializarse en la raíz del repositorio.

---

**Versión:** 1.0.0

**Estado:** Aprobado