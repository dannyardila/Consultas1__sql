# Consultas1__sql
# Introduccion a una consultas BD usando el lenguaje sql

## Base de datos: Ventas
## Tabla: cliente

![Tabla cliente](/img/tabla_cliente.png)

## Instruccion Select
-Permite seleccionar datos de una tabla.
-Su formato es:`SELECT campos_tablas FROM nombre_tabla`

### Consulta NO. 1
1.Para visualizar toda la informacion que contiene la tabla Cliente sse puede incluir con la instruccion SELECT el caracter **/*** o cada uno de los campos de la tabla.

-`SELECT * FROM Cliente`
![Consulta1](/img/consulta_1.png)

-`SELECT identificacion, nombre, apellidos, direccion, telefono, ciudad_nac, fecha_nac FROM Cliente`

![Consulta1_1](/img/consulta_2.png)

### Consulta No. 2

2. Para visualizar solamente la identificacion del cliente: `SELECT identificacion FROM Cliente`

![Consultas2](/img/Consultas_3.png)

### Consulta No. 3

3. Si se desea obtener los registros cuya iden tficacion sea mayor o igual a 150, se debe utilizar la clausula `WHERE` que especifica las condicciones que deben reunir los registros que van a seleccionar: `SELECT * FROM Cliente WHERE identificacion>=150`

![Consultas3](/img/Consultas_4.png)


### Consulta No. 4

4. Se desea obtener los registros cuyos apellidos sean Vanegas o Cetina, see debe utilizar el operador `IN` que especifica los registros que se quieren visualizar de una tabla.

`SELECT apellidos FROM Cliente WHERE apellidos IN ('Vanegas', Cetina')`

![Consultas4](/img/consultas_5.png)

O se puede utilizar el operador `OR`
`SELECT apellidos FROM Cliente WHERE apellidos ='Vanegas'OR apellidos = 'Cetina'`

![Consultas4](/img/Consultas_6.png)

### Consulta No. 5

5. Se desea obtener los registros cuya identificacion sea menor de 110 y la ciudad sea  Cali, se debe utilizar el operador `AND`

`SELECT * FROM Cliente WHERE identificacion<=110 AND ciudad_nac = 'Cali'`

![Consultas5](/img/consultas_7.png)

### Consulta No. 6

6. Si se desea obtener los registros cuyos nombres empiecen por la letra 'A', se debe utilizar el operador `LIKE` que utiliza los patrones `%` (todos)y `_` (caracter).

`SELECT * FROM Cliente WHERE nombre LIKE 'A%'`

![Consultas6](/img/consulta_8.png)

### Consulta No.7

7. Se desea obtener los registros cuyos nombres contengan la letra 'a'

`SELECT * FROM Cliente WHERE nombre LIKE '%a%'`


![Consultas7](/img/consultas_9.png)

### Consultas No.8

8. Se desea obtener los registros donde la cuarta letra del nombre del cliente sea la letra 'a'

`SELECT * FROM Cliente WHERE nombre LIKE '____a'`

![Consultas8](/img/Consultas_10.png)

### Consultas No. 9

9. Si se desea obtener los registros cuya identificacion este el intervalo 110 y 150, se debe utilizar la clausula `BETWEEN`, que sirve para especificar un intervalo de valores. 

`SELECT * FROM Cliente WHERE identificacion BETWEEN 110 AND 150`

![Consultas8](/img/consultas_11.png)


## Instrucion DELETE
-Permite borrar todos o un grupo especifico de registros de una tabla.

-Su formato es: `DELETE FROM nombre_tabla`

### Eliminacion No 1.

1. Eliminar los registros cuya identificacion mayor a 150

`DELETE FROM Cliente WHERE identificacion > 150`

![Eliminacion_1](/img/eliminacion_1.png)

2.Eliminar los registros cuya identificacion sea igual a 116

`DELETE FROM Cliente WHERE identificacion = 116`

![Eliminacion_2](/img/eliminacion_2.png)


## Instruccion UPDATE 

-Permite actualizar el campo de una tabla.

-Su formato es: `UPDATE nombre_tabla SET nombre_campo =Valor`

### Actualizacion No. 1

1.Para actualizar la ciudad de nacimiento de cristian Vanegas, cuya Identificacion es 114

`UPDATE Cliente SET ciudad_nac = 'Pereira' WHERE identificacion =114`

![Actualizacion_1](/img/Actualizacion_1.png)

## creacion tabla pedido

## Diccionario de datos

|Campo|Tipo de dato|Longitud|
|-----|------------|--------|
|**no_pedido**|varchar|15|
|iden_cliente|varchar|15|
|fecha_compra|date||
|fecha_vencimiento|date||
|Observacion|varchar|30|

![RELACION_1](/img/relacion_1.png)

### Tabla de pedidos por cliente 

![tabla_pedido](/img/tabla_pedidos.png)


## OPERADOR INNER JOIN 

-Permite obtener datos de dos o mas tablas.

-Cuando se realiza la concatenacion de las tablas no necesariamente se deben mostrar todos los datos de las tablas

-Su formato es:

`SELECT tabla1.ca, tabla2.campo, ... FROM tabla_principal INNER tabla_secundaria ON campo_comun_tabla1 = campo_comun_tabla2`

1. Para visualizar los campos identificacion, nombre, apellidos de la tabla Cliente y no_pedido, fecha_compra, fecha_vencimiento y obsrvacion de la tabla Pedido, se debe realizar la siguiente instruccion:

`SELECT Cliente,identificacion, Cliente.nombre, Cliente.apellidos, Pedido.no_pedido, Pedido. fecha_compra, Pedido.fecha_vencimiento, Pedido.observacion FROM Cliente INNER JOIN Pedido ON Cliente identificacion = Pedido.iden_cliente`

![INNER JOIN](/img/inner1.png)

