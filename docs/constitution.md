# Constitución del proyecto

## 1. Propósito

Establecer los principios, restricciones y reglas que gobiernan el desarrollo de Notes Manager, una prueba de concepto orientada a evaluar las capacidades de los agentes de desarrollo asistido por inteligencia artificial.

El objetivo es obtener un producto funcional, sencillo, mantenible y desplegable utilizando infraestructura gratuita, evaluando la capacidad de los agentes para interpretar instrucciones, planificar, implementar y validar soluciones.

## 2. Metodología de desarrollo

El proyecto adopta Spec-Driven Development (SDD) simplificado como metodología principal, complementado por los principios KISS, YAGNI y desarrollo incremental.

El desarrollo seguirá las siguientes fases:

1. CONSTITUTION: establecer los principios del proyecto.
2. SPECIFY: definir los requisitos funcionales.
3. PLAN: elaborar el plan de implementación.
4. TASKS: descomponer el plan en tareas verificables.
5. IMPLEMENT: inicializar el proyecto tecnológico y ejecutar las tareas aprobadas.
6. VALIDATE: verificar el cumplimiento de los requisitos.
7. DEPLOY: desplegar la aplicación.
8. EVALUATE: evaluar los resultados obtenidos.

Ninguna fase deberá ejecutarse anticipadamente sin autorización del responsable del proyecto.

## 3. Principios fundamentales

### P01. Simplicidad — KISS

La solución deberá utilizar la arquitectura más sencilla que permita satisfacer los requisitos establecidos.

Se deberá evitar:

- Sobreingeniería.
- Abstracciones innecesarias.
- Patrones de diseño sin justificación.
- Dependencias redundantes.
- Complejidad arquitectónica no requerida.

### P02. Alcance controlado — YAGNI

Solo se implementarán funcionalidades expresamente definidas en las especificaciones aprobadas.

No se deberán incorporar funcionalidades anticipadas, integraciones adicionales ni mejoras fuera del alcance autorizado.

Las oportunidades de mejora podrán documentarse como propuestas, pero no implementarse sin aprobación.

### P03. Desarrollo guiado por especificaciones

Las especificaciones aprobadas constituyen la fuente de verdad del proyecto.

El código deberá responder a los requisitos y criterios de aceptación establecidos.

Ante contradicciones, ambigüedades o información insuficiente, el agente deberá comunicar el problema antes de tomar decisiones que afecten el alcance, la arquitectura, la seguridad o el presupuesto.

### P04. Desarrollo incremental

La implementación deberá organizarse en incrementos funcionales pequeños y verificables.

Cada incremento deberá:

- Cumplir un objetivo definido.
- Mantener operativa la aplicación.
- Contar con validaciones apropiadas.
- Evitar regresiones sobre funcionalidades existentes.
- Generar evidencias de cumplimiento.

### P05. Calidad y mantenibilidad

El código deberá ser comprensible, consistente y mantenible.

Se priorizarán:

- Nombres descriptivos.
- Responsabilidades claramente definidas.
- Validación de entradas.
- Manejo adecuado de errores.
- Reutilización cuando esté justificada.
- Pruebas automatizadas relevantes.

No se deberá sacrificar la claridad del código por aplicar patrones o abstracciones innecesarias.

### P06. Control presupuestario

El presupuesto autorizado para infraestructura y servicios externos es de USD 0.

Solo se podrán utilizar servicios que dispongan de planes gratuitos compatibles con los requisitos del proyecto.

Se priorizarán servicios con cuotas gratuitas renovables y mecanismos que impidan consumos adicionales facturables.

Queda prohibido, sin autorización expresa:

- Contratar servicios de pago.
- Habilitar facturación.
- Activar planes premium.
- Contratar créditos adicionales.
- Activar pruebas gratuitas que puedan convertirse automáticamente en servicios de pago.
- Habilitar consumos adicionales facturables.

El agente deberá informar cualquier limitación relacionada con cuotas, capacidad, disponibilidad, renovación o compatibilidad de los servicios gratuitos.

### P07. Seguridad y protección de información

Las credenciales, tokens, claves de acceso y secretos no deberán incorporarse al código fuente ni al control de versiones.

La configuración sensible deberá gestionarse mediante variables de entorno.

Se utilizarán exclusivamente datos ficticios para el desarrollo y las pruebas.

No se expondrán públicamente operaciones de escritura, modificación o eliminación sin mecanismos de protección adecuados.

### P08. Autonomía controlada

El agente podrá tomar decisiones técnicas menores necesarias para ejecutar las tareas aprobadas.

No podrá modificar unilateralmente:

- Los requisitos funcionales.
- El alcance del proyecto.
- El stack tecnológico aprobado.
- Las restricciones arquitectónicas.
- Los criterios de aceptación.
- Las condiciones presupuestarias.
- Las reglas de esta constitución.

Las decisiones que excedan su autonomía deberán presentarse como propuestas para su aprobación.

### P09. Validación basada en evidencias

Una tarea no se considerará finalizada únicamente porque el código haya sido generado.

El agente deberá ejecutar las validaciones correspondientes y comunicar sus resultados.

Las evidencias deberán distinguir entre:

- CONFIRMADO: resultado respaldado por una validación ejecutada.
- INFERIDO: resultado deducido, pero no validado directamente.
- PENDIENTE: resultado que todavía requiere comprobación.
- BLOQUEADO: resultado que no puede comprobarse debido a una limitación identificada.

No se deberán declarar pruebas exitosas que no hayan sido ejecutadas.

### P10. Documentación y lenguaje

La documentación, especificaciones, planes, tareas e informes deberán redactarse en español.

Los identificadores técnicos del código, clases, funciones, variables, endpoints y nombres de archivos deberán mantenerse en inglés.

La documentación deberá mantenerse alineada con el comportamiento real de la aplicación.

### P11. Trazabilidad y control de cambios

Los cambios deberán estar asociados a requisitos o tareas previamente definidos.

Se utilizará Git como sistema de control de versiones y Conventional Commits como convención para los mensajes de commit.

No se deberán realizar operaciones destructivas sobre el repositorio ni eliminar información existente sin autorización.

### P12. Transparencia

El agente deberá comunicar:

- Decisiones técnicas asumidas.
- Errores encontrados.
- Limitaciones identificadas.
- Dependencias incorporadas.
- Validaciones ejecutadas.
- Tareas pendientes.
- Desviaciones respecto al plan aprobado.

No deberá ocultar problemas ni presentar resultados parciales como implementaciones completas.

### P13. Inicialización tecnológica

El proyecto comenzará con un repositorio Git y los documentos de especificación aprobados.

La inicialización del framework, generación de archivos de configuración, instalación de dependencias y creación de la estructura del código fuente serán responsabilidad del agente.

Estas actividades solo podrán ejecutarse durante la fase IMPLEMENT, después de aprobar el plan y las tareas correspondientes.

El agente deberá:

- Respetar las versiones tecnológicas aprobadas.
- Conservar los documentos iniciales.
- Evitar sobrescribir archivos existentes.
- Evitar estructuras de proyectos anidados innecesarias.
- Validar que la aplicación inicializada pueda compilarse y ejecutarse.

## 4. Independencia y condiciones del experimento

La constitución es independiente del proveedor de inteligencia artificial y del modelo utilizado.

Para esta prueba de concepto, la interacción con los agentes se realizará exclusivamente desde las interfaces gráficas de los IDE seleccionados.

Se permite utilizar la terminal integrada para ejecutar comandos relacionados con el desarrollo.

No se permite delegar tareas a agentes CLI adicionales ni incorporar otros asistentes de inteligencia artificial sin autorización.

Las implementaciones deberán realizarse de manera independiente, utilizando las mismas especificaciones, restricciones y criterios de aceptación.

No se deberá reutilizar código generado por otra implementación participante en el experimento.

## 5. Jerarquía documental

Los documentos del proyecto tendrán el siguiente orden de autoridad:

1. constitution.md
2. specification.md
3. architecture.md
4. acceptance.md
5. AGENTS.md
6. plan.md
7. tasks.md

Los documentos generados durante la planificación y ejecución no podrán contradecir los principios ni las restricciones previamente aprobadas.

Ante un conflicto documental, el agente deberá informar la inconsistencia y solicitar su resolución.

## 6. Definición de terminado

Una tarea se considerará terminada cuando:

- La implementación cumpla los requisitos asociados.
- Las validaciones correspondientes hayan sido ejecutadas satisfactoriamente.
- No existan regresiones conocidas relacionadas con el cambio.
- La documentación relevante se encuentre actualizada.
- Las evidencias y limitaciones hayan sido comunicadas.
- No se hayan introducido cambios fuera del alcance autorizado.

## 7. Gobierno de la constitución

La presente constitución solo podrá modificarse mediante autorización expresa del responsable del proyecto.

Toda modificación deberá registrar su justificación, versión e impacto sobre el desarrollo.

Los agentes de inteligencia artificial no están autorizados a modificar unilateralmente este documento.

---

**Versión:** 1.0.0

**Estado:** Aprobado

**Metodología:** Spec-Driven Development simplificado

**Ámbito:** Notes Manager — AI Agent Proof of Concept