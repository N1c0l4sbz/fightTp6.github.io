# TP6 — Base de datos, normalización y SQL

**Proyecto:** Impact Fight  

## Objetivo del trabajo

Diseñar una base relacional en MySQL, explicar la normalización hasta tercera forma normal y ejecutar consultas `INSERT`, `SELECT`, `UPDATE`, `DELETE` y `INNER JOIN`.

## Estructura de datos observada

Las capturas de phpMyAdmin muestran la base **`lunar_mca`** con siete tablas: `categorias`, `consultas`, `detalle_pedidos`, `pedidos`, `productos`, `roles` y `usuarios`. El Diseñador permite ver relaciones vinculadas con categorías y productos, usuarios y roles, y pedidos con sus detalles. Los campos y relaciones deben coincidir con `schema.sql`.

La organización relacional ayuda a evitar duplicación de información: una categoría se registra una vez, los productos guardan su referencia, y los detalles de pedido representan los productos involucrados en cada operación.

### Normalización

- **1FN:** cada campo contiene un dato indivisible, por ejemplo un precio o una cantidad, no una lista mezclada de productos.
- **2FN:** los atributos dependen de toda la clave a la que pertenecen, como los campos propios de una línea de pedido.
- **3FN:** los datos descriptivos de la categoría y del usuario se mantienen en sus tablas y se vinculan por identificadores, evitando dependencias innecesarias.

## Evidencias disponibles del TP6

**1. Tablas creadas en phpMyAdmin.**

![Estructura de la base lunar mca con siete tablas](../capturas%20baez/carpeta%20baez%20tp6/tablas-mysql.png)

**2. Relaciones entre las tablas en el Diseñador.**

![Diagrama de relaciones entre categorías productos usuarios y pedidos](../capturas%20baez/carpeta%20baez%20tp6/relaciones%20de%20tablas.png)

**3. Consulta `SELECT` con `JOIN` y resultados.**

![Consulta SQL con JOIN y resultado de productos categorías](../capturas%20baez/carpeta%20baez%20tp6/select-mysql.png)

## Evidencias que todavía faltan en el ZIP

- Una captura de `INSERT` ejecutado con un registro ficticio.
- Una captura de `UPDATE` con cláusula `WHERE` aplicada a ese registro.
- Una captura de `DELETE` con cláusula `WHERE` que elimine exclusivamente ese registro de prueba.
- Una captura o sentencia `SELECT` con `WHERE` y `ORDER BY`, si no está ya documentada en `consultas.sql`.

El TP6 debe incluir también los archivos **`schema.sql`**, **`consultas.sql`** y **`NORMALIZACION.md`**. **No estaban dentro del ZIP de capturas recibido**, por lo que hay que conservar los archivos SQL reales del proyecto y no sustituirlos por ejemplos genéricos.

## Pruebas

Abrir `http://localhost/phpmyadmin/`, seleccionar la base `lunar_mca`, revisar **Estructura** y **Diseñador** y ejecutar las consultas SQL sobre datos ficticios. Confirmar que las relaciones están definidas, los resultados coinciden y las modificaciones no afectan información real.

## Conclusión

La normalización y las relaciones permiten mantener los datos del catálogo y de los usuarios de manera organizada, y las consultas SQL permiten leer y modificar registros de forma controlada.
