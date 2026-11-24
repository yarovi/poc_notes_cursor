# Especificación funcional — Notes Manager

## 1. Objetivo

Desarrollar una aplicación web que permita registrar, consultar, modificar, eliminar y organizar notas personales de manera sencilla.

## 2. Actor

Usuario: persona que administra las notas mediante la interfaz web.

## 3. Modelo de información

### Nota

| Campo | Descripción | Obligatorio |
|---|---|---|
| id | Identificador único | Sí |
| title | Título de la nota | Sí |
| content | Contenido de la nota | Sí |
| category | Categoría de clasificación | Sí |
| status | Estado de la nota | Sí |
| createdAt | Fecha y hora de creación | Sí |
| updatedAt | Fecha y hora de última modificación | Sí |

### Estados

- ACTIVE: nota activa.
- ARCHIVED: nota archivada.

### Categorías

- PERSONAL: personal.
- WORK: trabajo.
- STUDY: estudio.
- OTHER: otros.

## 4. Requisitos funcionales

| ID | Funcionalidad | Descripción |
|---|---|---|
| RF-01 | Crear nota | Registrar una nota con título, contenido y categoría. |
| RF-02 | Listar notas | Visualizar las notas registradas. |
| RF-03 | Consultar nota | Visualizar el contenido completo de una nota. |
| RF-04 | Editar nota | Modificar el título, contenido y categoría. |
| RF-05 | Eliminar nota | Eliminar una nota previa confirmación del usuario. |
| RF-06 | Buscar notas | Buscar coincidencias por título o contenido. |
| RF-07 | Filtrar notas | Filtrar por categoría y estado. |
| RF-08 | Archivar nota | Cambiar el estado de ACTIVE a ARCHIVED. |
| RF-09 | Restaurar nota | Cambiar el estado de ARCHIVED a ACTIVE. |

## 5. Reglas de negocio

| ID | Regla |
|---|---|
| RN-01 | Cada nota tendrá un identificador único generado automáticamente. |
| RN-02 | El título tendrá entre 1 y 100 caracteres. |
| RN-03 | El contenido tendrá entre 1 y 5000 caracteres. |
| RN-04 | El título y contenido no podrán estar vacíos ni contener únicamente espacios. |
| RN-05 | La categoría deberá pertenecer al catálogo definido. |
| RN-06 | Toda nota nueva tendrá el estado ACTIVE. |
| RN-07 | Las fechas de creación y modificación se generarán automáticamente. |
| RN-08 | La fecha de creación no podrá modificarse. |
| RN-09 | La fecha de modificación se actualizará al editar, archivar o restaurar una nota. |
| RN-10 | La eliminación será definitiva y requerirá confirmación. |
| RN-11 | Archivar una nota no eliminará su información. |
| RN-12 | La búsqueda no distinguirá entre mayúsculas y minúsculas. |
| RN-13 | La búsqueda y los filtros podrán combinarse. |
| RN-14 | Las notas deberán conservarse después de cerrar o recargar la aplicación. |
| RN-15 | El listado se ordenará por fecha de última modificación descendente. |

## 6. Interfaz funcional

### Pantalla principal

- Listado de notas.
- Buscador por título o contenido.
- Filtro por categoría.
- Filtro por estado.
- Acción para crear una nota.
- Acciones para consultar, editar, eliminar, archivar o restaurar.

Por defecto, se mostrarán las notas activas.

### Formulario de nota

- Campo de título.
- Campo de contenido.
- Selector de categoría.
- Acción para guardar.
- Acción para cancelar.
- Mensajes de validación.

El formulario podrá utilizarse para crear y editar notas.

### Detalle de nota

Mostrará toda la información registrada y las acciones correspondientes.

### Confirmación de eliminación

Permitirá confirmar o cancelar la eliminación de una nota.

## 7. Comportamiento de la interfaz

La aplicación deberá comunicar:

- Operaciones realizadas satisfactoriamente.
- Errores de validación.
- Errores durante las operaciones.
- Estados de carga.
- Ausencia de notas registradas.
- Ausencia de resultados de búsqueda.

La interfaz deberá adaptarse a dispositivos de escritorio y móviles.

## 8. Fuera del alcance

- Registro y gestión de usuarios.
- Gestión dinámica de categorías.
- Archivos adjuntos.
- Recordatorios y notificaciones.
- Compartir notas.
- Edición colaborativa.
- Exportación e importación de notas.
- Historial de versiones.
- Funcionalidades de inteligencia artificial.

---

**Versión:** 1.0.0

**Estado:** Propuesto para aprobación