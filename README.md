# ObvioScript

## Grupo 03

### Integrantes

- Juan Felipe Valencia Gallego
- Sebastian Guevara Perez
- Santiago Sosa Marin
- Karol Valeria Barrios Ordoñez

---

# 1. Dominio o contexto del sistema

El dominio seleccionado para ObvioScript es la **gestión de un centro de realidad virtual**.

ObvioScript será un lenguaje formal basado en reglas que permitirá representar decisiones relacionadas con el funcionamiento de un centro de experiencias de realidad virtual.

El sistema permitirá procesar situaciones relacionadas con:

- Usuarios.
- Estaciones de realidad virtual.
- Reservas.
- Experiencias VR.
- Tiempo de sesión.
- Disponibilidad.
- Métodos de pago.
- Batería de visores y controles.
- Mantenimiento de equipos.
- Capacidad de las experiencias.

Las reglas permitirán tomar decisiones dependiendo del estado de los usuarios, las estaciones, las reservas y los dispositivos.

Una característica distintiva de ObvioScript es el uso de expresiones coloquiales, sarcásticas y cotidianas como palabras reservadas.

Por ejemplo:

OBVIO_BOBIS estacion_disponible = CLARO_QUE_SI  
Y_ENTONCES permitir_reserva

Esta expresión representa conceptualmente:

SI estacion_disponible = true  
ENTONCES permitir_reserva

La idea es mantener una estructura formal y procesable, pero utilizando un vocabulario propio, divertido y fácil de reconocer.

---

# 2. Reglas del sistema

Las siguientes 15 reglas representan situaciones que ObvioScript deberá ser capaz de procesar.

## Regla 1

**Regla en lenguaje natural:**  
Si una estación está disponible, entonces se debe permitir realizar una reserva.

**ObvioScript:**

OBVIO_BOBIS estacion_disponible = CLARO_QUE_SI  
Y_ENTONCES permitir_reserva

---

## Regla 2

**Regla en lenguaje natural:**  
Si la batería del visor es menor que 20, entonces se debe generar una alerta de batería.

**ObvioScript:**

OBVIO_BOBIS bateria_visor < 20  
Y_ENTONCES generar_alerta_bateria

---

## Regla 3

**Regla en lenguaje natural:**  
Si una estación está en mantenimiento, entonces se debe bloquear su uso.

**ObvioScript:**

OBVIO_BOBIS mantenimiento = CLARO_QUE_SI  
Y_ENTONCES bloquear_estacion

---

## Regla 4

**Regla en lenguaje natural:**  
Si una estación está disponible y el pago está confirmado, entonces se debe iniciar la sesión.

**ObvioScript:**

OBVIO_BOBIS estacion_disponible = CLARO_QUE_SI  
ENCIMA pago_confirmado = CLARO_QUE_SI  
Y_ENTONCES iniciar_sesion

---

## Regla 5

**Regla en lenguaje natural:**  
Si el usuario tiene una edad mayor o igual a 12 años y la experiencia está disponible, entonces se debe permitir la experiencia.

**ObvioScript:**

OBVIO_BOBIS edad >= 12  
ENCIMA experiencia_disponible = CLARO_QUE_SI  
Y_ENTONCES permitir_experiencia

---

## Regla 6

**Regla en lenguaje natural:**  
Si la estación está en mantenimiento o la batería del visor es menor que 10, entonces se debe bloquear la estación.

**ObvioScript:**

OBVIO_BOBIS mantenimiento = CLARO_QUE_SI  
O_QUE bateria_visor < 10  
Y_ENTONCES bloquear_estacion

---

## Regla 7

**Regla en lenguaje natural:**  
Si el tiempo de sesión es mayor o igual a 60 minutos y la sesión está activa, entonces se debe finalizar la sesión.

**ObvioScript:**

OBVIO_BOBIS tiempo_sesion >= 60  
ENCIMA sesion_activa = CLARO_QUE_SI  
Y_ENTONCES finalizar_sesion

---

## Regla 8

**Regla en lenguaje natural:**  
Si el método de pago es tarjeta o transferencia, entonces se debe habilitar el pago digital.

**ObvioScript:**

OBVIO_BOBIS metodo_pago = "tarjeta"  
O_QUE metodo_pago = "transferencia"  
Y_ENTONCES habilitar_pago_digital

---

## Regla 9

**Regla en lenguaje natural:**  
Si el usuario tiene una reserva activa y el pago está confirmado, entonces se debe asignar una estación.

**ObvioScript:**

OBVIO_BOBIS reserva_activa = CLARO_QUE_SI  
ENCIMA pago_confirmado = CLARO_QUE_SI  
Y_ENTONCES asignar_estacion

---

## Regla 10

**Regla en lenguaje natural:**  
Si no existen estaciones disponibles o el centro no está abierto, entonces se debe rechazar la reserva.

**ObvioScript:**

OBVIO_BOBIS estaciones_disponibles = 0  
O_QUE centro_abierto = NI_POR_EL_PUTAS  
Y_ENTONCES rechazar_reserva

---

## Regla 11

**Regla en lenguaje natural:**  
Si la experiencia es multijugador y existen al menos dos usuarios, entonces se debe iniciar la experiencia multijugador.

**ObvioScript:**

OBVIO_BOBIS experiencia_multijugador = CLARO_QUE_SI  
ENCIMA cantidad_usuarios >= 2  
Y_ENTONCES iniciar_multijugador

---

## Regla 12

**Regla en lenguaje natural:**  
Si la batería del control es menor o igual a 15 y existe un control de repuesto, entonces se debe reemplazar el control.

**ObvioScript:**

OBVIO_BOBIS bateria_control <= 15  
ENCIMA control_repuesto = CLARO_QUE_SI  
Y_ENTONCES reemplazar_control

---

## Regla 13

**Regla en lenguaje natural:**  
Si el valor de la sesión es mayor o igual a 50000 y el usuario es miembro, entonces se debe aplicar un descuento.

**ObvioScript:**

OBVIO_BOBIS valor_sesion >= 50000.0  
ENCIMA usuario_miembro = CLARO_QUE_SI  
Y_ENTONCES aplicar_descuento

---

## Regla 14

**Regla en lenguaje natural:**  
Si la experiencia seleccionada es "terror" y el usuario es menor de 16 años, entonces se debe solicitar autorización.

**ObvioScript:**

OBVIO_BOBIS experiencia = "terror"  
ENCIMA edad < 16  
Y_ENTONCES solicitar_autorizacion

---

## Regla 15

**Regla en lenguaje natural:**  
Si la estación está disponible, el pago está confirmado y el equipo no está en mantenimiento, entonces se debe habilitar la experiencia.

**ObvioScript:**

OBVIO_BOBIS estacion_disponible = CLARO_QUE_SI  
ENCIMA pago_confirmado = CLARO_QUE_SI  
ENCIMA mantenimiento = NI_POR_EL_PUTAS  
Y_ENTONCES habilitar_experiencia

---

# 3. Clasificación de variables

| Variable | Tipo de dato en Java | Ejemplo de valor |
|---|---|---|
| edad | int | 17 |
| bateria_visor | int | 75 |
| bateria_control | int | 50 |
| tiempo_sesion | int | 45 |
| estaciones_disponibles | int | 4 |
| cantidad_usuarios | int | 2 |
| valor_sesion | double | 45000.0 |
| estacion_disponible | boolean | true |
| mantenimiento | boolean | false |
| pago_confirmado | boolean | true |
| experiencia_disponible | boolean | true |
| sesion_activa | boolean | true |
| reserva_activa | boolean | true |
| centro_abierto | boolean | true |
| experiencia_multijugador | boolean | true |
| control_repuesto | boolean | true |
| usuario_miembro | boolean | false |
| metodo_pago | String | "tarjeta" |
| experiencia | String | "terror" |

---

# 4. Tipos de datos propios de ObvioScript

ObvioScript utilizará nombres propios para representar los tipos de datos.

| Tipo tradicional | Nombre en ObvioScript |
|---|---|
| int | CUENTE_PUES |
| double | CON_DECIMALES_Y_TODO |
| boolean | SI_O_NO_PUES |
| String | ECHE_EL_CUENTO |
| List | TODOS_ESOS |

Ejemplos:

CUENTE_PUES edad = 17

CON_DECIMALES_Y_TODO valor_sesion = 45000.0

SI_O_NO_PUES pago_confirmado = CLARO_QUE_SI

ECHE_EL_CUENTO experiencia = "terror"

---

# 5. Sintaxis formal

La estructura general de una regla será:

OBVIO_BOBIS <condicion> Y_ENTONCES <accion>

Una regla con dos condiciones obligatorias será:

OBVIO_BOBIS <condicion>  
ENCIMA <condicion>  
Y_ENTONCES <accion>

Una regla con una condición alternativa será:

OBVIO_BOBIS <condicion>  
O_QUE <condicion>  
Y_ENTONCES <accion>

La definición formal será:

<regla> ::= OBVIO_BOBIS <condicion> Y_ENTONCES <accion>

<condicion> ::= <comparacion>
              | <comparacion> ENCIMA <condicion>
              | <comparacion> O_QUE <condicion>

<comparacion> ::= <variable> <operador> <valor>

<operador> ::= > | < | >= | <= | = | !=

<variable> ::= identificador_en_minusculas

<valor> ::= numero
          | CLARO_QUE_SI
          | NI_POR_EL_PUTAS
          | "texto"

<accion> ::= identificador_en_minusculas

---

# 6. Convención de escritura

ObvioScript utilizará una convención de escritura uniforme.

- Las palabras reservadas se escribirán en mayúsculas.
- Las expresiones de varias palabras utilizarán guion bajo.
- Las variables se escribirán en minúsculas.
- Las variables compuestas utilizarán guion bajo.
- Las acciones se escribirán en minúsculas.
- Los textos se escribirán entre comillas dobles.
- CLARO_QUE_SI representará un valor verdadero.
- NI_POR_EL_PUTAS representará un valor falso.
- OBVIO_BOBIS iniciará una condición.
- Y_ENTONCES introducirá la acción.
- ENCIMA representará la unión lógica Y.
- O_QUE representará la unión lógica O.
- Los operadores permitidos serán >, <, >=, <=, = y !=.
- Las reglas deberán mantener la estructura establecida en la sintaxis formal.

---

# 7. Verificación de requisitos

## Reglas con una sola condición

Las siguientes reglas contienen una sola condición:

- Regla 1.
- Regla 2.
- Regla 3.

Esto cumple con el requisito de tener al menos tres reglas con una sola condición.

## Reglas con condiciones compuestas

Las reglas 4 a 15 utilizan condiciones compuestas mediante ENCIMA u O_QUE.

Esto cumple con el requisito de tener al menos tres reglas con condiciones compuestas utilizando Y u O.

## Reglas que combinan diferentes tipos de datos

### Ejemplo 1

OBVIO_BOBIS edad >= 12  
ENCIMA experiencia_disponible = CLARO_QUE_SI  
Y_ENTONCES permitir_experiencia

En esta regla se combinan:

edad -> int  
experiencia_disponible -> boolean

### Ejemplo 2

OBVIO_BOBIS valor_sesion >= 50000.0  
ENCIMA usuario_miembro = CLARO_QUE_SI  
Y_ENTONCES aplicar_descuento

En esta regla se combinan:

valor_sesion -> double  
usuario_miembro -> boolean

Esto cumple con el requisito de combinar diferentes tipos de datos.

---

# 8. Resumen del lenguaje

Las principales palabras utilizadas actualmente son:

OBVIO_BOBIS -> SI  
Y_ENTONCES -> ENTONCES  
ENCIMA -> Y  
O_QUE -> O  
CLARO_QUE_SI -> true  
NI_POR_EL_PUTAS -> false

ObvioScript busca mantener una estructura formal clara, pero utilizar un vocabulario coloquial, sarcástico y fácil de reconocer.