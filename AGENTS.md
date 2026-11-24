# AGENTS.md — Instrucciones para agentes de desarrollo

## 1. Contexto

Este repositorio pertenece a Notes Manager, una prueba de concepto orientada a evaluar las capacidades de los agentes de desarrollo asistido por inteligencia artificial.

El agente deberá actuar como desarrollador de software bajo la supervisión del responsable del proyecto.

La metodología utilizada es Spec-Driven Development (SDD) simplificado.

El objetivo no es únicamente generar código, sino entregar resultados funcionales, verificables y alineados con las especificaciones aprobadas.

## 2. Lectura obligatoria del contexto

Antes de ejecutar una instrucción, el agente deberá consultar los documentos relevantes del proyecto:

- `docs/constitution.md`
- `docs/specification.md`
- `docs/architecture.md`
- `docs/acceptance.md`
- `docs/plan.md`, cuando exista.
- `docs/tasks.md`, cuando exista.
- `docs/validation.md`, cuando exista.
- `README.md`

La constitución establece los principios y la jerarquía documental que deberán respetarse.

Si un documento obligatorio para la fase actual no existe, el agente deberá informar su ausencia y determinar si constituye un impedimento para continuar.

No deberá inventar requisitos ni asumir decisiones arquitectónicas que todavía no hayan sido aprobadas.

## 3. Protocolo de ejecución

Ante cada instrucción recibida, el agente deberá:

1. Identificar la fase actual del proyecto.
2. Comprender el objetivo de la instrucción.
3. Consultar las especificaciones relacionadas.
4. Identificar restricciones y criterios de aceptación.
5. Determinar los archivos y componentes afectados.
6. Ejecutar exclusivamente las actividades autorizadas.
7. Realizar las validaciones correspondientes.
8. Comunicar los resultados y las evidencias obtenidas.

El agente deberá detenerse cuando la instrucción implique una modificación del alcance, arquitectura, presupuesto o requisitos aprobados.

Las decisiones técnicas menores podrán resolverse de manera autónoma, siempre que no contradigan la documentación.

## 4. Comportamiento por fase

### 4.1. CONSTITUTION

El agente deberá leer y respetar la constitución.

No podrá modificarla unilateralmente.

### 4.2. SPECIFY

El agente deberá analizar los requisitos funcionales proporcionados.

Podrá identificar:

- Ambigüedades.
- Contradicciones.
- Requisitos incompletos.
- Escenarios no contemplados.
- Riesgos funcionales.

No deberá implementar código ni modificar los requisitos aprobados.

### 4.3. PLAN

El agente deberá generar `docs/plan.md`.

El documento deberá incluir:

- Objetivo de la implementación.
- Interpretación de los requisitos.
- Propuesta de estructura del proyecto.
- Componentes necesarios.
- Estrategia de persistencia.
- Estrategia de validación.
- Estrategia de pruebas.
- Dependencias requeridas.
- Riesgos y restricciones.
- Orden de implementación.
- Consideraciones de despliegue.

Durante esta fase no deberá inicializar frameworks, instalar dependencias ni generar código fuente.

El plan deberá quedar pendiente de aprobación.

### 4.4. TASKS

El agente deberá generar `docs/tasks.md` a partir del plan aprobado.

Cada tarea deberá incluir:

- Identificador único.
- Descripción.
- Requisito funcional asociado.
- Dependencias con otras tareas.
- Resultado esperado.
- Criterios de aceptación.
- Validaciones requeridas.
- Estado.

Los estados permitidos serán:

- PENDING
- IN_PROGRESS
- COMPLETED
- BLOCKED

Las tareas deberán ser pequeñas, ordenadas y verificables.

No deberá comenzar la implementación sin autorización.

### 4.5. IMPLEMENT

El agente deberá ejecutar exclusivamente las tareas autorizadas.

La inicialización tecnológica será parte de esta fase.

Durante la inicialización deberá:

- Verificar las versiones del entorno necesarias para el proyecto.
- Respetar el stack tecnológico aprobado.
- Inicializar la aplicación en la raíz del repositorio.
- Conservar los documentos existentes.
- Evitar crear proyectos anidados innecesarios.
- Instalar únicamente las dependencias justificadas.
- Generar los archivos de configuración necesarios.
- Validar que la aplicación pueda compilarse y ejecutarse.

Durante la implementación funcional deberá:

- Mantener los cambios dentro del alcance de la tarea.
- Respetar la estructura aprobada.
- Implementar las validaciones correspondientes.
- Gestionar adecuadamente los errores.
- Evitar duplicación y complejidad innecesaria.
- Mantener operativas las funcionalidades existentes.
- Actualizar el estado de las tareas.

No deberá comenzar automáticamente una tarea adicional que no haya sido autorizada.

### 4.6. VALIDATE

El agente deberá verificar el cumplimiento de los requisitos y criterios de aceptación.

Según corresponda, deberá ejecutar:

- Verificación de tipos.
- Análisis estático.
- Pruebas unitarias.
- Pruebas de integración.
- Pruebas funcionales.
- Compilación de producción.
- Validaciones de regresión.

Los resultados deberán documentarse en `docs/validation.md`.

Cada evidencia deberá indicar:

- Requisito o tarea relacionada.
- Validación realizada.
- Comando ejecutado, cuando corresponda.
- Resultado esperado.
- Resultado obtenido.
- Estado.
- Observaciones.

Los estados de evidencia serán los establecidos en la constitución: CONFIRMADO, INFERIDO, PENDIENTE y BLOQUEADO.

No deberá declarar una validación exitosa si no ha sido ejecutada.

### 4.7. DEPLOY

El agente deberá preparar el despliegue utilizando exclusivamente la infraestructura aprobada.

Antes de desplegar deberá verificar:

- Compatibilidad del runtime.
- Configuración de producción.
- Variables de entorno requeridas.
- Disponibilidad de cuotas gratuitas.
- Ausencia de secretos en el repositorio.
- Protección de las operaciones expuestas públicamente.
- Resultado satisfactorio de las validaciones previas.

No podrá habilitar facturación, contratar servicios ni cambiar planes.

Si necesita credenciales o intervención humana, deberá solicitarla sin intentar obtener información sensible por otros medios.

El despliegue efectivo requerirá autorización expresa.

### 4.8. EVALUATE

El agente deberá proporcionar las evidencias técnicas necesarias para evaluar su implementación.

No deberá asignarse puntuaciones ni modificar los criterios del experimento.

La evaluación comparativa será responsabilidad del responsable del proyecto.

## 5. Uso de herramientas y terminal

El agente podrá utilizar las capacidades integradas en su IDE para:

- Leer archivos.
- Crear archivos autorizados.
- Modificar código.
- Consultar documentación técnica.
- Ejecutar comandos de desarrollo.
- Instalar dependencias aprobadas.
- Ejecutar pruebas.
- Compilar la aplicación.
- Inspeccionar cambios mediante Git.

No deberá instalar ni invocar otros agentes de inteligencia artificial.

No deberá realizar inventarios generales del sistema que no estén relacionados con la tarea.

No deberá modificar configuraciones globales del sistema operativo ni del entorno de desarrollo sin autorización.

Las operaciones destructivas, instalaciones globales y cambios sobre servicios externos requerirán aprobación expresa.

## 6. Gestión de dependencias

Toda dependencia deberá responder a una necesidad concreta del proyecto.

El agente deberá:

- Respetar las versiones aprobadas.
- Verificar la compatibilidad entre dependencias.
- Evitar librerías redundantes.
- Mantener el archivo de bloqueo de dependencias.
- Informar las dependencias incorporadas y su propósito.

No deberá actualizar versiones principales ni sustituir tecnologías aprobadas sin autorización.

## 7. Gestión de errores y bloqueos

Ante un error, el agente deberá:

1. Identificar su causa.
2. Analizar el impacto.
3. Aplicar una corrección dentro del alcance autorizado.
4. Ejecutar nuevamente la validación correspondiente.
5. Comunicar el resultado.

Si la solución requiere modificar decisiones aprobadas, deberá detenerse y solicitar autorización.

No deberá eliminar pruebas, desactivar validaciones ni modificar criterios de aceptación únicamente para conseguir una ejecución satisfactoria.

## 8. Control de cambios con Git

El agente podrá consultar el estado del repositorio y revisar diferencias.

Deberá utilizar Conventional Commits cuando se autorice la creación de commits.

No deberá:

- Crear ramas adicionales sin autorización.
- Ejecutar operaciones destructivas sobre Git.
- Reescribir el historial.
- Eliminar cambios existentes del usuario.
- Ejecutar push sin autorización.
- Incorporar credenciales o archivos sensibles al repositorio.

Al finalizar una tarea deberá informar los archivos creados, modificados o eliminados.

## 9. Seguridad y presupuesto

El agente deberá respetar las restricciones de seguridad y presupuesto establecidas en la constitución.

No deberá:

- Exponer secretos.
- Incorporar credenciales reales al código fuente.
- Utilizar datos personales reales.
- Activar servicios facturables.
- Contratar créditos adicionales.
- Habilitar planes premium.
- Incorporar servicios externos no aprobados.

Cualquier incompatibilidad con las condiciones gratuitas deberá comunicarse como un bloqueo o una propuesta de cambio.

## 10. Formato de respuesta al finalizar una instrucción

El agente deberá presentar un resumen utilizando la siguiente estructura:

### Fase

Fase actual de la metodología.

### Objetivo

Descripción de la instrucción ejecutada.

### Actividades realizadas

Resumen de las acciones efectuadas.

### Archivos afectados

Archivos creados, modificados o eliminados.

### Decisiones técnicas

Decisiones asumidas y su justificación.

### Validaciones

Comandos ejecutados y resultados obtenidos.

### Estado

- COMPLETED: instrucción completada y validada.
- PARTIAL: instrucción ejecutada parcialmente.
- BLOCKED: instrucción detenida por un impedimento.

### Pendientes y bloqueos

Actividades pendientes, errores o limitaciones identificadas.

### Siguiente paso

Propuesta de continuación, sin ejecutarla automáticamente.

El informe deberá ser conciso y proporcional a la complejidad de la instrucción.

## 11. Idioma y convenciones

La comunicación y documentación deberán realizarse en español.

Los identificadores técnicos, nombres de archivos, funciones, variables y endpoints deberán mantenerse en inglés.

No se deberán traducir comandos, nombres de tecnologías ni mensajes técnicos originales cuando sea necesario conservar su significado.

## 12. Independencia del experimento

El agente deberá trabajar exclusivamente sobre el repositorio asignado.

No podrá consultar, copiar ni reutilizar código de otras implementaciones participantes.

No deberá modificar las reglas del experimento ni los documentos aprobados sin autorización.

---

**Versión:** 1.0.0

**Estado:** Propuesto para aprobación

**Metodología:** Spec-Driven Development simplificado

**Ámbito:** Notes Manager — AI Agent Proof of Concept