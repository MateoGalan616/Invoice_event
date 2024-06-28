### Base de datos: invoice
## nombre_cliente | fecha_compra | nombre_producto | cantidad
```
CREATE VIEW invoice_detail AS
SELECT
  client.fullname AS nombre_cliente,
  invoice.create_at AS fecha_compra,
  product.description AS nombre_producto,
  detail.quantity AS cantidad
FROM
  client
JOIN
  invoice ON client.id = invoice.client_id
JOIN
  detail ON invoice.id = detail.invoice_id
JOIN
  product ON detail.product_id = product.id;

```

## Funcion:
# Este código permite unir las 4 tablas existentes en la Base de Datos "invoice" para así obtener una vista que permita al usuario ver el nombre del cliente, junto a la fecha de compra (dato existente en la tabla invoice), nombre_producto (dato existente en la tabla product) y la cantidad del mismo (dato existente en la tabla detail).

## Captura: 

<img src="./Capturas/invoice_detail.png"


## Crear una vista donde se muestre la lista de miembros registrados a las conferencias.
### Base de datos: event
### nombre_conferencia | codigo_registro | nombre_miembro 

## Código SQL:

```
CREATE VIEW confCode_regCode_member AS
SELECT
  conference.title AS nombre_conferencia,
  register.code AS codigo_registro,
  member.fullname AS nombre_miembro
FROM
  conference
INNER JOIN
  register ON conference.id = register.conference_id
INNER JOIN
  member ON register.member_id = member.id;

```

## Funcion: 
## Este código permite al usuario obtener los siguientes datos: nombre_conferencia (datos existentes en la tabla conference), código_registro (datos existentes en la tabla register) y nombre_miembro (datos existentes en la tabla member).

## Captura: 

<img src="./Capturas/evento_conference.png" 


