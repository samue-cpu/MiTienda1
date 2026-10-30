<!--
Informe de impacto de sincronización (temporal; retirar antes del commit):
- Versión: plantilla sin ratificar → 1.0.0 (adopción inicial).
- Principios definidos: I. Simplicidad ante todo; II. Idioma y mercado;
  III. Cero alcance fantasma; IV. Verificable por una persona no técnica;
  V. Datos del usuario con respeto.
- Secciones completadas: Core Principles; Alcance y tecnologías;
  Flujo de desarrollo y verificación; Governance.
- Secciones eliminadas: ninguna.
- Plantillas y comandos: sin modificaciones; consultan la constitución en ejecución.
- Pendientes y marcadores diferidos: ninguno.
-->
# MiTienda Constitution

## Core Principles

### I. Simplicidad ante todo

La primera versión DEBE ser sencilla, funcional y fácil de utilizar. El desarrollo DEBE
priorizar el catálogo de ropa y accesorios, la administración de productos, el carrito y
los pedidos mediante WhatsApp.

Cada decisión técnica DEBE resolver una necesidad del alcance especificado. NO DEBEN
introducirse funcionalidades innecesarias, abstracciones sin uso actual ni complejidad
anticipada. La solución más simple que cumpla los requisitos y proteja los datos DEBE
ser la opción predeterminada, para facilitar el mantenimiento y la validación del producto.

### II. Idioma y mercado

Toda la interfaz DEBE utilizar español de Perú, incluidos formularios, validaciones,
mensajes de error y el mensaje de pedido generado para WhatsApp. Los precios, subtotales
y totales DEBEN mostrarse en soles peruanos con el símbolo S/ y dos decimales.

La interfaz DEBE ser clara, ordenada y adaptable a celulares y computadoras. Los flujos
del catálogo, carrito y administración DEBEN poder utilizarse en ambos tamaños de pantalla,
con controles legibles y sin que el contenido impida completar las acciones principales.

### III. Cero alcance fantasma

Solo DEBEN implementarse funcionalidades definidas en la especificación aprobada. Toda
funcionalidad nueva DEBE proponerse al responsable del proyecto y obtener su autorización
antes de incorporarse a la especificación, al plan, a las tareas y al código.

NO DEBEN implementarse pagos en línea, pasarelas de pago, pagos con tarjetas ni integraciones
de pago con Yape o Plin. El cierre del carrito DEBE preparar el pedido para WhatsApp;
no constituye un pago ni una confirmación automática de venta.

Las mejoras técnicas DEBEN mantenerse dentro del alcance aprobado. Una suposición del
desarrollador o de Codex NO constituye autorización para agregar funciones. Esta regla evita
que el producto crezca sin una necesidad y una decisión explícitas.

### IV. Verificable por una persona no técnica

Cada funcionalidad DEBE tener criterios de aceptación observables mediante el uso de la
aplicación, sin revisar código, consultar la base de datos ni ejecutar comandos técnicos.
Como mínimo, la validación funcional DEBE demostrar que:

- El administrador puede agregar, editar y eliminar productos desde la interfaz, y los
  cambios se reflejan en el catálogo.
- El cliente puede visualizar los productos y sus precios en soles.
- El cliente puede agregar productos al carrito y consultar sus cantidades y total.
- Al finalizar el pedido, se abre WhatsApp con un mensaje preparado que incluye los
  productos del carrito, sus cantidades y el total en soles.
- El mensaje coincide con el contenido del carrito; el envío lo realiza el cliente en WhatsApp.

La evidencia de aceptación DEBE describir pasos reproducibles y resultados esperados en
lenguaje sencillo. Las pruebas técnicas complementan esta comprobación y NO la sustituyen.

### V. Datos del usuario con respeto

Solo DEBEN solicitarse los datos necesarios para gestionar el pedido. Los clientes NO
DEBEN registrarse ni iniciar sesión para consultar el catálogo, utilizar el carrito o
preparar el pedido por WhatsApp. NO DEBE almacenarse información personal innecesaria.

El acceso del administrador DEBE estar protegido mediante autenticación y autorización.
El backend DEBE verificar los permisos en cada operación de creación, edición y eliminación
de productos; ocultar botones en la interfaz no es una medida suficiente.

Las contraseñas y los secretos NO DEBEN guardarse directamente en el código, exponerse en
el frontend ni incluirse en Git o GitHub. Los secretos DEBEN suministrarse mediante
configuración externa. Si se almacenan contraseñas, DEBEN persistirse mediante un hash
seguro para contraseñas, nunca como texto plano. Los datos recibidos DEBEN validarse en
el backend y los errores o registros NO DEBEN revelar credenciales ni datos personales
innecesarios. Estas medidas protegen al administrador y minimizan la exposición del cliente.

## Alcance y tecnologías

MiTienda es un sistema web de tienda virtual que funciona como catálogo de ropa y
accesorios. Su alcance inicial comprende la administración de productos, su consulta
pública, el carrito y la preparación de pedidos mediante WhatsApp, sin pagos en línea.

Las tecnologías obligatorias son:

- Frontend: React con Vite.
- Backend: Node.js.
- Base de datos: SQLite.
- Control de versiones: Git y GitHub.
- Metodología: Spec-Driven Development (SDD), utilizando Spec Kit y Codex.

Los productos DEBEN persistirse en SQLite a través del backend. La interfaz, la lógica
del servidor y el acceso a datos DEBEN mantener responsabilidades claras. Las dependencias
y decisiones de diseño DEBEN justificarse por necesidades de la especificación. Cambiar
estas tecnologías requiere una enmienda aprobada de esta constitución.

## Flujo de desarrollo y verificación

El desarrollo DEBE seguir la secuencia constitución, especificación, plan, tareas,
implementación y validación. Spec Kit y Codex DEBEN consultar esta constitución al generar
o revisar los artefactos de cada funcionalidad.

Antes de implementar, la especificación DEBE delimitar el alcance y los criterios de
aceptación. El plan DEBE comprobar el cumplimiento de los cinco principios y de las
tecnologías obligatorias. Cada tarea DEBE poder vincularse con un requisito aprobado o
con una necesidad técnica indispensable para satisfacerlo.

Antes de dar un cambio por terminado, su revisión DEBE comprobar el alcance, el español
de Perú, los importes en soles, el uso en celulares y computadoras, la protección del
administrador y el tratamiento mínimo de datos. DEBEN ejecutarse las comprobaciones
funcionales aplicables y las pruebas técnicas proporcionales al cambio, con atención al
cálculo del carrito, al mensaje de WhatsApp y a la autorización del backend.

Los resultados y las limitaciones detectadas DEBEN registrarse en los artefactos de la
funcionalidad. Los incumplimientos de aceptación o de esta constitución DEBEN corregirse
antes de declarar completado el trabajo. Git y GitHub DEBEN conservar cambios revisables
y trazables a la especificación, excluyendo secretos y datos personales reales.

## Governance

Esta constitución es obligatoria durante todo el desarrollo de MiTienda. Prevalece sobre
plantillas, planes, tareas y decisiones de implementación que la contradigan. Cada revisión
DEBE comprobar su cumplimiento; los artefactos incompatibles DEBEN corregirse antes de
continuar con el trabajo afectado.

Una enmienda DEBE documentar la regla que cambia, el motivo y el impacto sobre las
especificaciones, el diseño, las tareas y la aplicación existente. El responsable del
proyecto DEBE aprobarla explícitamente antes de aplicarla. Tras la aprobación, DEBEN
actualizarse esta constitución y los artefactos afectados, incluyendo un plan de adaptación
cuando corresponda. No se permiten excepciones implícitas por conveniencia técnica.

La versión DEBE seguir el formato MAJOR.MINOR.PATCH: MAJOR para eliminar o redefinir
principios de manera incompatible; MINOR para añadir principios o ampliar obligaciones;
PATCH para aclaraciones o correcciones sin cambios de significado. Cada enmienda DEBE
actualizar la fecha de modificación y conservar la fecha de ratificación original.

**Version**: 1.0.0 | **Ratified**: 2026-10-30 | **Last Amended**: 2026-10-30
