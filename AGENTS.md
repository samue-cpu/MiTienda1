# MiTienda: Sistema Web de Tienda Virtual

Catálogo web de ropa y accesorios. El administrador agrega, edita y elimina productos.
Los clientes visualizan productos, los agregan al carrito y realizan pedidos mediante
WhatsApp. No se realizan pagos en línea.

## Tecnologías

- Frontend: React con Vite.
- Backend: Node.js con Express.
- Base de datos: SQLite.
- Control de versiones: Git y GitHub.
- Metodología: Spec-Driven Development (SDD) con Spec Kit y Codex.

## Ejecución y pruebas locales

Todavía no existe ningún `package.json`: no hay comandos definidos para instalar
dependencias, iniciar el frontend o el backend ni ejecutar pruebas. Al crearlos,
documentar aquí los comandos de instalación según el gestor elegido y los scripts
reales de inicio y pruebas de cada `package.json`, con su directorio de ejecución.
No inventar comandos ni indicar como disponibles scripts que no existan.

## Convenciones

- Usar español de Perú y mostrar precios en soles (S/).
- Mantener código sencillo, limpio y organizado e interfaz adaptable a celulares y computadoras.
- Implementar solo lo especificado; proponer y obtener autorización para nuevas funciones.
- No implementar pagos en línea; los pedidos se realizan mediante WhatsApp.
- Proteger el acceso y las credenciales del administrador; no guardar contraseñas ni secretos en el código.
- Seguir la constitución y el flujo SDD: especificación, plan, tareas, implementación y validación.

Las reglas de producto viven en .specify/memory/constitution.md y el estado del producto en specs/README.md
