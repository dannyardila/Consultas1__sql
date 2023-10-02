# Consultas1__sql
# Introduccion a una consultas BD usando el lenguaje sql

## Base de datos: Ventas
## Tabla: cliente

![Tabla cliente](tabla_cliente.png)

## Instruccion Select
-Permite seleccionar datos de una tabla.
-Su formato es:`SELECT campos_tablas FROM nombre_tabla`

### Consulta NO. 1
1.Para visualizar toda la informacion que contiene la tabla Cliente sse puede incluir con la instruccion SELECT el caracter **/*** o cada uno de los campos de la tabla.

-`SELECT * FROM Cliente`
![Consulta1](consulta_1.png)

-`SELECT identificacion, nombre, apellidos, direccion, telefono, ciudad_nac, fecha_nac FROM Cliente`

![Consulta2](consulta_2.png)

### Consulta No. 2

2. Para visualizar solamente la identificacion del cliente: `SELECT iden tificacion FROM Cliente`

![Consultas3](Consultas_3.png)
