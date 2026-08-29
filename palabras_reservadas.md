# Palabras reservadas de CaféScript

Las palabras reservadas son elementos propios del lenguaje que tienen un significado específico dentro de la sintaxis de CaféScript.

Para mantener la identidad del lenguaje, las palabras reservadas están relacionadas con conceptos propios de una cafetería.

---

## 1. Palabras clave

| Palabra reservada | Significado                   | Categoría     |
| ----------------- | ----------------------------- | ------------- |
| `ESPRESSO`        | Inicia una condición          | Palabra clave |
| `CAPUCHINO`       | Indica el inicio de la acción | Palabra clave |

---

## 2. Operadores lógicos

| Palabra reservada | Significado                                         | Categoría       |
| ----------------- | --------------------------------------------------- | --------------- |
| `LATTE`           | Une condiciones que deben cumplirse simultáneamente | Operador lógico |
| `MOCHA`           | Une condiciones alternativas                        | Operador lógico |

---

## 3. Literales booleanos

| Palabra reservada | Significado                   | Categoría        |
| ----------------- | ----------------------------- | ---------------- |
| `DULCE`           | Representa un valor verdadero | Literal booleano |
| `AMARGO`          | Representa un valor falso     | Literal booleano |

---

# 4. Operadores de comparación

CaféScript utilizará los siguientes operadores de comparación:

| Operador | Significado       | Categoría           |
| -------- | ----------------- | ------------------- |
| `>`      | Mayor que         | Operador relacional |
| `<`      | Menor que         | Operador relacional |
| `>=`     | Mayor o igual que | Operador relacional |
| `<=`     | Menor o igual que | Operador relacional |
| `=`      | Igual que         | Operador relacional |
| `!=`     | Diferente de      | Operador relacional |

---

# 5. Significado de las palabras reservadas

## ESPRESSO

Inicia una condición dentro de una regla.

Equivalente conceptual:

```text
SI
```

Ejemplo:

```text
ESPRESSO stock_cafe < 10 CAPUCHINO generar_alerta_inventario
```

---

## CAPUCHINO

Indica el inicio de la acción que se ejecutará cuando la condición sea verdadera.

Equivalente conceptual:

```text
ENTONCES
```

Ejemplo:

```text
ESPRESSO disponible = DULCE CAPUCHINO habilitar_venta
```

---

## LATTE

Permite unir dos o más condiciones que deben cumplirse.

Equivalente conceptual:

```text
Y
```

Ejemplo:

```text
ESPRESSO stock_cafe > 0 LATTE stock_leche > 0 CAPUCHINO preparar_capuchino
```

---

## MOCHA

Permite unir condiciones alternativas.

Equivalente conceptual:

```text
O
```

Ejemplo:

```text
ESPRESSO producto = "cafe" MOCHA producto = "capuchino" CAPUCHINO clasificar_bebida_caliente
```

---

## DULCE

Representa un valor booleano verdadero.

Equivalente:

```text
true
```

Ejemplo:

```text
ESPRESSO disponible = DULCE CAPUCHINO habilitar_venta
```

---

## AMARGO

Representa un valor booleano falso.

Equivalente:

```text
false
```

Ejemplo:

```text
ESPRESSO disponible = AMARGO CAPUCHINO bloquear_venta
```

---

# 6. Tipos de datos utilizados

Aunque los tipos de datos corresponden principalmente a la clasificación de variables del README, los valores que podrá utilizar CaféScript serán:

## Enteros

Representan cantidades, stock y edades.

Ejemplos:

```text
0
5
10
22
```

Tipo Java:

```text
int
```

## Decimales

Representan precios y valores de compra.

Ejemplos:

```text
8500.0
50000.0
100000.0
```

Tipo Java:

```text
double
```

## Booleanos

Se representan mediante:

```text
DULCE
AMARGO
```

Correspondencia:

```text
DULCE  → true
AMARGO → false
```

Tipo Java:

```text
boolean
```

## Texto

Los valores de texto se escriben entre comillas dobles.

Ejemplos:

```text
"cafe"
"capuchino"
"tarjeta"
"transferencia"
```

Tipo Java:

```text
String
```

---

# 7. Convención de escritura

CaféScript utilizará las siguientes convenciones:

* Las palabras reservadas se escriben en mayúsculas.
* Las variables se escriben en minúsculas.
* Las variables compuestas utilizan guion bajo.
* Las acciones se escriben en minúsculas.
* Los textos utilizan comillas dobles.
* Los valores booleanos se representan mediante `DULCE` y `AMARGO`.
* Los operadores relacionales se escriben utilizando los símbolos definidos.
* Las reglas comienzan con `ESPRESSO`.
* Las acciones están precedidas por `CAPUCHINO`.
* Las condiciones múltiples se conectan mediante `LATTE` o `MOCHA`.

---

# 8. Ejemplo completo

```text
ESPRESSO cliente_registrado = DULCE LATTE total_compra >= 50000 CAPUCHINO aplicar_beneficio_cliente
```

Componentes:

```text
ESPRESSO             → Palabra clave
cliente_registrado   → Variable
=                    → Operador relacional
DULCE                → Literal booleano
LATTE                → Operador lógico
total_compra         → Variable
>=                   → Operador relacional
50000                → Valor numérico
CAPUCHINO            → Palabra clave
aplicar_beneficio_cliente → Acción
```
