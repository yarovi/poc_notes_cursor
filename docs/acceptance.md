# Criterios de aceptación — Notes Manager

## 1. Objetivo

Verificar el cumplimiento de los requisitos funcionales definidos en `docs/specification.md` y las restricciones técnicas de `docs/architecture.md`.

## 2. Escenarios funcionales

| ID | Requisito | Escenario | Resultado esperado |
|---|---|---|---|
| CA-01 | RF-01 | Crear una nota con datos válidos. | Nota registrada con estado ACTIVE, identificador y fechas generadas. |
| CA-02 | RF-01 | Crear una nota con campos obligatorios vacíos o espacios. | Operación rechazada con mensajes de validación. |
| CA-03 | RF-01 | Crear una nota excediendo los límites permitidos. | Operación rechazada. |
| CA-04 | RF-01 | Registrar una categoría inválida. | Operación rechazada. |
| CA-05 | RF-02 | Consultar el listado con notas registradas. | Se muestran las notas activas ordenadas por última modificación descendente. |
| CA-06 | RF-02 | Consultar el listado sin notas registradas. | Se muestra un mensaje informativo. |
| CA-07 | RF-03 | Consultar una nota existente. | Se muestra toda su información. |
| CA-08 | RF-03 | Consultar una nota inexistente. | Se informa que la nota no existe. |
| CA-09 | RF-04 | Editar una nota con datos válidos. | Se guardan los cambios, se conserva createdAt y se actualiza updatedAt. |
| CA-10 | RF-04 | Editar una nota con datos inválidos. | Se rechazan los cambios y se conserva la información anterior. |
| CA-11 | RF-05 | Confirmar la eliminación de una nota. | La nota se elimina definitivamente. |
| CA-12 | RF-05 | Cancelar la eliminación. | La nota permanece sin modificaciones. |
| CA-13 | RF-06 | Buscar una coincidencia parcial por título. | Se muestran las notas coincidentes. |
| CA-14 | RF-06 | Buscar por contenido utilizando diferentes mayúsculas y minúsculas. | Se muestran las coincidencias independientemente de la capitalización. |
| CA-15 | RF-06 | Buscar un texto inexistente. | Se informa que no existen resultados. |
| CA-16 | RF-07 | Filtrar por categoría. | Se muestran únicamente las notas de la categoría seleccionada dentro del estado seleccionado. |
| CA-17 | RF-07 | Filtrar por estado. | Se muestran únicamente las notas del estado seleccionado. |
| CA-18 | RF-06, RF-07 | Combinar búsqueda, categoría y estado. | Los resultados cumplen todas las condiciones seleccionadas. |
| CA-19 | RF-08 | Archivar una nota activa. | Cambia a ARCHIVED, actualiza updatedAt y conserva su información. |
| CA-20 | RF-09 | Restaurar una nota archivada. | Cambia a ACTIVE y actualiza updatedAt. |

## 3. Escenarios transversales

| ID | Escenario | Resultado esperado |
|---|---|---|
| CA-21 | Recargar o cerrar y volver a abrir la aplicación. | Las notas registradas permanecen disponibles. |
| CA-22 | Cancelar la creación o edición. | No se persisten cambios. |
| CA-23 | Ejecutar una operación mientras se procesa una solicitud. | La interfaz comunica el estado de carga. |
| CA-24 | Simular un error del backend. | La interfaz informa el error sin presentar una confirmación falsa. |
| CA-25 | Utilizar la aplicación desde escritorio y móvil. | Las funcionalidades permanecen accesibles y utilizables. |

## 4. Validaciones técnicas

| ID | Validación | Resultado esperado |
|---|---|---|
| CT-01 | Verificación de tipos TypeScript. | Sin errores. |
| CT-02 | Análisis estático. | Sin errores. |
| CT-03 | Pruebas unitarias. | Todas las pruebas ejecutadas satisfactoriamente. |
| CT-04 | Pruebas funcionales. | Todos los escenarios automatizados ejecutados satisfactoriamente. |
| CT-05 | Compilación de producción. | Compilación satisfactoria. |
| CT-06 | Contratos REST. | Cumplimiento de los endpoints y códigos HTTP definidos en architecture.md. |
| CT-07 | Persistencia en Firestore. | Las operaciones se reflejan correctamente en la base de datos. |
| CT-08 | Seguridad. | Sin credenciales expuestas ni operaciones públicas desprotegidas. |
| CT-09 | Despliegue en Vercel. | Aplicación accesible y funcional mediante el mecanismo de acceso aprobado. |
| CT-10 | Presupuesto. | Infraestructura operativa dentro de los planes gratuitos aprobados. |

## 5. Registro de resultados

El agente deberá documentar los resultados en `docs/validation.md`, indicando:

- Identificador del criterio.
- Evidencia obtenida.
- Resultado: PASS, FAIL, PENDING o BLOCKED.

Los criterios deberán verificarse utilizando datos ficticios.

La aplicación se considerará aceptada cuando todos los criterios obligatorios hayan obtenido el resultado PASS.

---

**Versión:** 1.0.0

**Estado:** Propuesto para aprobación