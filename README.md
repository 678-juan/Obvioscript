# CaféScript ☕

## Nombre del grupo

**Grupo X**

## Integrantes

* Integrante 1
* Integrante 2
* Integrante 3
* Integrante 4

---

# 1. Dominio o contexto del sistema

El dominio seleccionado para CaféScript es la **gestión de una cafetería**.

CaféScript será un lenguaje de programación orientado a representar reglas relacionadas con las operaciones de una cafetería.

El sistema permitirá procesar situaciones relacionadas con:

* Productos.
* Precios.
* Cantidades.
* Inventario.
* Disponibilidad.
* Clientes.
* Métodos de pago.
* Ventas.
* Descuentos.
* Pedidos.

Las reglas permitirán tomar decisiones dependiendo de las características y estados de los productos, clientes e inventario.

La temática del lenguaje estará relacionada con el contexto de una cafetería, por lo que las palabras reservadas utilizarán nombres asociados con bebidas y conceptos propios de este dominio.

---

# 2. Reglas del sistema

Las siguientes 15 reglas representan situaciones que CaféScript deberá ser capaz de procesar.

## Regla 1

**Regla en lenguaje natural:**
Si el stock de café es menor que 10, entonces se debe generar una alerta de inventario.

```text
ESPRESSO stock_cafe < 10 CAPUCHINO generar_alerta_inventario
```

---

## Regla 2

**Regla en lenguaje natural:**
Si el precio del producto es mayor o igual a 15000, entonces se debe marcar como producto costoso.

```text
ESPRESSO precio >= 15000 CAPUCHINO marcar_producto_costoso
```

---

## Regla 3

**Regla en lenguaje natural:**
Si el producto está disponible, entonces se debe habilitar su venta.

```text
ESPRESSO disponible = DULCE CAPUCHINO habilitar_venta
```

---

## Regla 4

**Regla en lenguaje natural:**
Si existe stock de café y existe stock de leche, entonces se puede preparar un capuchino.

```text
ESPRESSO stock_cafe > 0 LATTE stock_leche > 0 CAPUCHINO preparar_capuchino
```

---

## Regla 5

**Regla en lenguaje natural:**
Si el precio es menor o igual a 10000 y la cantidad solicitada es mayor o igual a 3, entonces se debe aplicar un descuento por cantidad.

```text
ESPRESSO precio <= 10000 LATTE cantidad >= 3 CAPUCHINO aplicar_descuento_cantidad
```

---

## Regla 6

**Regla en lenguaje natural:**
Si el producto es café o el producto es capuchino, entonces se debe clasificar como bebida caliente.

```text
ESPRESSO producto = "cafe" MOCHA producto = "capuchino" CAPUCHINO clasificar_bebida_caliente
```

---

## Regla 7

**Regla en lenguaje natural:**
Si el stock es menor o igual a 5 y el producto está activo, entonces se debe solicitar reabastecimiento.

```text
ESPRESSO stock <= 5 LATTE activo = DULCE CAPUCHINO solicitar_reabastecimiento
```

---

## Regla 8

**Regla en lenguaje natural:**
Si el método de pago es tarjeta o el método de pago es transferencia, entonces se debe confirmar el pago.

```text
ESPRESSO metodo_pago = "tarjeta" MOCHA metodo_pago = "transferencia" CAPUCHINO confirmar_pago
```

---

## Regla 9

**Regla en lenguaje natural:**
Si el cliente está registrado y el total de la compra es mayor o igual a 50000, entonces se debe aplicar un beneficio.

```text
ESPRESSO cliente_registrado = DULCE LATTE total_compra >= 50000 CAPUCHINO aplicar_beneficio_cliente
```

---

## Regla 10

**Regla en lenguaje natural:**
Si la cantidad disponible es igual a 0 o el producto no está disponible, entonces se debe bloquear la venta.

```text
ESPRESSO cantidad = 0 MOCHA disponible = AMARGO CAPUCHINO bloquear_venta
```

---

## Regla 11

**Regla en lenguaje natural:**
Si existe stock, el producto está activo y el producto está disponible, entonces se debe habilitar el producto.

```text
ESPRESSO stock > 0 LATTE activo = DULCE LATTE disponible = DULCE CAPUCHINO habilitar_producto
```

---

## Regla 12

**Regla en lenguaje natural:**
Si el stock es menor o igual a 10 y el producto está activo, entonces se debe generar una alerta de inventario.

```text
ESPRESSO stock <= 10 LATTE activo = DULCE CAPUCHINO generar_alerta_inventario
```

---

## Regla 13

**Regla en lenguaje natural:**
Si el total de la compra es mayor o igual a 100000 y el cliente está registrado, entonces se debe aplicar un descuento especial.

```text
ESPRESSO total_compra >= 100000 LATTE cliente_registrado = DULCE CAPUCHINO aplicar_descuento_especial
```

---

## Regla 14

**Regla en lenguaje natural:**
Si la edad del cliente es menor de 18 o el cliente no está registrado, entonces se debe solicitar una verificación.

```text
ESPRESSO edad < 18 MOCHA cliente_registrado = AMARGO CAPUCHINO solicitar_verificacion_cliente
```

---

## Regla 15

**Regla en lenguaje natural:**
Si el producto es café, la cantidad solicitada es mayor o igual a 5 y el producto está disponible, entonces se debe preparar un pedido mayorista.

```text
ESPRESSO producto = "cafe" LATTE cantidad >= 5 LATTE disponible = DULCE CAPUCHINO preparar_pedido_mayorista
```

---

# 3. Clasificación de variables

| Nombre de la variable | Tipo de dato en Java | Ejemplo de valor |
| --------------------- | -------------------- | ---------------- |
| stock_cafe            | int                  | 15               |
| stock_leche           | int                  | 8                |
| cantidad              | int                  | 5                |
| stock                 | int                  | 10               |
| edad                  | int                  | 22               |
| precio                | double               | 8500.0           |
| total_compra          | double               | 75000.0          |
| disponible            | boolean              | true             |
| activo                | boolean              | true             |
| cliente_registrado    | boolean              | false            |
| producto              | String               | "cafe"           |
| metodo_pago           | String               | "tarjeta"        |

---

# 4. Sintaxis formal

La estructura general de una regla será:

```text
ESPRESSO <condicion> CAPUCHINO <accion>
```

Una regla puede contener una condición simple:

```text
ESPRESSO <condicion> CAPUCHINO <accion>
```

También puede contener condiciones compuestas mediante `LATTE`:

```text
ESPRESSO <condicion> LATTE <condicion> CAPUCHINO <accion>
```

o mediante `MOCHA`:

```text
ESPRESSO <condicion> MOCHA <condicion> CAPUCHINO <accion>
```

La definición formal será:

```text
<regla> ::= ESPRESSO <condicion> CAPUCHINO <accion>

<condicion> ::= <comparacion>
              | <comparacion> LATTE <condicion>
              | <comparacion> MOCHA <condicion>

<comparacion> ::= <variable> <operador> <valor>

<operador> ::= > | < | >= | <= | = | !=

<variable> ::= identificador_en_minusculas

<valor> ::= numero | DULCE | AMARGO | "texto"

<accion> ::= identificador_en_minusculas
```

---

# 5. Convención de escritura

CaféScript utilizará una convención de escritura uniforme.

1. Las palabras reservadas se escribirán en mayúsculas.
2. Las variables se escribirán en minúsculas.
3. Las variables compuestas utilizarán guion bajo.
4. Las acciones se escribirán en minúsculas.
5. Los textos se escribirán entre comillas dobles.
6. `DULCE` representará un valor verdadero.
7. `AMARGO` representará un valor falso.
8. `ESPRESSO` iniciará una condición.
9. `CAPUCHINO` separará la condición de la acción.
10. `LATTE` representará la unión lógica `Y`.
11. `MOCHA` representará la unión lógica `O`.
12. Los operadores de comparación permitidos serán `>`, `<`, `>=`, `<=`, `=` y `!=`.
13. Las reglas deberán mantener el formato definido en la sintaxis formal.

---

# 6. Verificación de los requisitos de las reglas

## Reglas con una sola condición

Las siguientes reglas contienen una sola condición:

* Regla 1.
* Regla 2.
* Regla 3.

Esto cumple con el requisito de tener al menos tres reglas con una sola condición.

## Reglas con condiciones compuestas

Las siguientes reglas utilizan condiciones compuestas mediante `LATTE` u `MOCHA`:

* Regla 4.
* Regla 5.
* Regla 6.
* Regla 7.
* Regla 8.
* Regla 9.
* Regla 10.
* Regla 11.
* Regla 12.
* Regla 13.
* Regla 14.
* Regla 15.

Esto cumple con el requisito de tener al menos tres reglas con condiciones compuestas utilizando `Y` u `O`.

## Reglas que combinan diferentes tipos de datos

### Ejemplo 1

```text
ESPRESSO cantidad > 0 LATTE disponible = DULCE CAPUCHINO habilitar_venta
```

En esta regla se combinan:

```text
cantidad   → int
disponible → boolean
```

### Ejemplo 2

```text
ESPRESSO total_compra >= 50000 LATTE cliente_registrado = DULCE CAPUCHINO aplicar_beneficio_cliente
```

En esta regla se combinan:

```text
total_compra       → double
cliente_registrado → boolean
```

Esto cumple con el requisito de combinar diferentes tipos de datos.

---

# 7. Resumen del lenguaje

CaféScript utiliza una sintaxis inspirada en conceptos de una cafetería.

Las principales palabras utilizadas son:

```text
ESPRESSO   → Inicia una condición
CAPUCHINO  → Indica la acción
LATTE      → Une condiciones mediante Y
MOCHA      → Une condiciones mediante O
DULCE      → Representa true
AMARGO     → Representa false
```

El lenguaje está diseñado para que las reglas sean fáciles de leer, manteniendo una temática relacionada con el dominio seleccionado.
