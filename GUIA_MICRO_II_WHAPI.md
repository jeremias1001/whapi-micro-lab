# Guia paso a paso Microeconomia II con caso Whapi

Objetivo: estudiar para la prueba usando el caso de Whapi.pro como hilo conductor. La idea no es reemplazar la materia, sino hacer que las formulas se peguen mejor: Whapi es una empresa SaaS que debe elegir planes de precios para distintos tipos de clientes.

## 0. Mapa rapido de la prueba

La prueba se ordena en seis bloques:

1. Herramientas base: demanda, ingreso, costos, beneficios y bienestar.
2. Discriminacion de precios: primer, segundo y tercer grado.
3. Tarifa en dos partes y menus de planes.
4. Ventas atadas y paquetes.
5. Oligopolio: Cournot, Bertrand y Stackelberg.
6. Teoria de juegos: Nash, estrategias dominantes, maximin, dilema del prisionero y juegos repetidos.

La parte mas conectada con Whapi es discriminacion de precios tipo 2: la empresa no observa perfectamente el tipo de cliente, entonces ofrece un menu de planes para que cada cliente se autoseleccione.

---

# 1. Herramientas base

## 1.1 Demanda directa e inversa

Demanda directa:

```text
Q = a - P
```

Demanda inversa:

```text
P = a - Q
```

Interpretacion:

- `Q` es cantidad demandada.
- `P` es precio.
- `a` mide el tamano maximo del mercado o disposicion a pagar maxima.

Caso Whapi:

```text
Q_pequenas(P) = 120 - 3P
Q_medianas(P) = 180 - 2P
Q_grandes(P) = 260 - P
```

Lectura: las empresas pequenas son mas sensibles al precio; si sube el precio, se van mas rapido.

## 1.2 Ingreso total

```text
IT = P * Q
```

Si `P = a - Q`:

```text
IT = (a - Q)Q = aQ - Q^2
```

## 1.3 Ingreso marginal

```text
IMg = dIT/dQ
```

Si:

```text
P = a - bQ
```

entonces:

```text
IMg = a - 2bQ
```

Regla clave: en monopolio, para maximizar beneficios se cumple:

```text
IMg = CMg
```

## 1.4 Costos

Costo marginal:

```text
CMg = dCT/dQ
```

Si:

```text
CT = cQ
```

entonces:

```text
CMg = c
```

Si:

```text
CT = aQ + bQ^2
```

entonces:

```text
CMg = a + 2bQ
```

Caso Whapi:

- Costo fijo: servidores, desarrollo, soporte base.
- Costo marginal: costo adicional de atender mas conversaciones, mensajes, IA, API, almacenamiento.
- Como SaaS, el costo marginal suele ser menor que el precio mensual, pero no es cero.

## 1.5 Beneficio

```text
pi = IT - CT
pi = P(Q)Q - CT(Q)
```

En oligopolio:

```text
pi_i = P(Q)q_i - CT_i(q_i)
```

---

# 2. Bienestar

## 2.1 Excedente del consumidor

Es la diferencia entre lo que el consumidor estaba dispuesto a pagar y lo que efectivamente paga.

Si:

```text
Q = a - P
```

entonces:

```text
EC = (a - P)^2 / 2
```

Forma general:

```text
EC = integral_0^Q P(q)dq - PQ
```

Ejemplo:

```text
Q = 30 - P
P = 10
EC = (30 - 10)^2 / 2 = 200
```

Caso Whapi:

Si una tienda pagaria hasta 80 USD porque recupera ventas por WhatsApp, pero paga 39 USD, su excedente es parte del valor recuperado menos el pago.

## 2.2 Excedente del productor

```text
EP = IT - CV
```

Si no hay costos fijos:

```text
EP = pi
```

## 2.3 Bienestar total

```text
BT = EC + EP
```

Tambien:

```text
BT = integral_0^Q P(q)dq - CT(Q)
```

## 2.4 Perdida social

En monopolio o Cournot puede haber menos cantidad que en competencia perfecta. La perdida social mide el bienestar que se pierde por esa menor produccion.

```text
PS = 1/2 * (Q_CP - Q_M) * (P_M - CMg)
```

---

# 3. Discriminacion de precios

## 3.1 Condiciones para discriminar

Una empresa puede discriminar precios si cumple:

1. Tiene poder de mercado.
2. Puede separar consumidores o hacer que se autoseleccionen.
3. Puede limitar arbitraje.
4. Hay diferencias en disposicion a pagar o elasticidad.

Caso Whapi:

- Poder de mercado: diferenciacion por IA + WhatsApp + CRM + pagos.
- Segmentos distintos: pequena, mediana, grande.
- Arbitraje limitado: no es facil revender un plan SaaS.
- Disposicion a pagar distinta: una empresa grande pierde mas dinero si no responde WhatsApp.

## 3.2 Primer grado

La empresa cobra a cada consumidor exactamente su disposicion maxima a pagar.

```text
EC = 0
pi = integral_0^Q P(q)dq - CT(Q)
P(Q) = CMg
```

Resultado:

- Cantidad eficiente.
- Todo el excedente va a la empresa.
- Es dificil de aplicar porque requiere conocer la disposicion a pagar individual.

Caso Whapi:

Seria cobrarle a cada cliente exactamente lo que Whapi le genera en valor. En la practica es dificil, salvo contratos enterprise muy personalizados.

## 3.3 Segundo grado

La empresa no observa directamente el tipo del consumidor. Entonces crea un menu de planes.

Planes:

```text
Plan bajo: (Q_b, T_b)
Plan alto: (Q_a, T_a)
```

Utilidad:

```text
U_i = V_i(Q) - T
```

Restricciones de participacion:

```text
V_b(Q_b) - T_b >= 0
V_a(Q_a) - T_a >= 0
```

Restricciones de autoseleccion:

```text
V_b(Q_b) - T_b >= V_b(Q_a) - T_a
V_a(Q_a) - T_a >= V_a(Q_b) - T_b
```

Normalmente:

- La participacion del tipo bajo queda activa.
- La autoseleccion del tipo alto queda activa.
- El tipo alto recibe renta informativa.
- El plan bajo queda distorsionado para que el alto no quiera imitarlo.

## 3.4 Tercer grado

La empresa separa grupos observables y cobra precios distintos.

Regla:

```text
IMg_1 = CMg
IMg_2 = CMg
```

O:

```text
(P_i - CMg) / P_i = -1 / elasticidad_i
```

El grupo con demanda mas inelastica paga mas.

Caso Whapi:

Seria cobrar distinto segun pais, industria o tamano observable de empresa. En cambio, tipo 2 es mas elegante para SaaS: menus Starter, Plus y Pro.

---

# 4. Tarifa en dos partes

## 4.1 Formula general

```text
T(Q) = F + P * Q
```

Donde:

- `F`: cargo fijo.
- `P`: precio por unidad.
- `Q`: cantidad consumida.

Beneficio:

```text
pi = nF + (P - CMg)Q
```

Caso Whapi:

- `F`: mensualidad del plan.
- `P`: cargo por conversacion extra, usuario extra o uso adicional.
- `Q`: conversaciones, leads, contactos o mensajes.

## 4.2 Tarifa unica en dos partes

Supongamos dos tipos:

```text
Q_1 = a_1 - P
Q_2 = a_2 - P
a_2 > a_1
```

Como la tarifa es unica, el cargo fijo debe permitir que el tipo bajo participe:

```text
F = EC_1(P)
F = (a_1 - P)^2 / 2
```

Demanda total:

```text
Q_T = n_1(a_1 - P) + n_2(a_2 - P)
```

Beneficio:

```text
pi(P) = (n_1+n_2)F + (P-c)[n_1(a_1-P)+n_2(a_2-P)]
```

Paso a paso:

1. Escribe `F = EC_bajo(P)`.
2. Escribe `Q_T`.
3. Sustituye en `pi(P)`.
4. Deriva respecto a `P`.
5. Igualas a cero.
6. Obtienes `P*`.
7. Calculas `F*`, cantidades y beneficio.

## 4.3 Ejercicio resuelto: tarifa unica

Datos:

```text
Q_1 = 30 - P
Q_2 = 40 - P
c = 5
n_1 = 3
n_2 = 2
```

Cargo fijo:

```text
F = (30 - P)^2 / 2
```

Cantidad total:

```text
Q_T = 3(30-P) + 2(40-P)
Q_T = 170 - 5P
```

Beneficio:

```text
pi(P) = 5 * [(30-P)^2/2] + (P-5)(170-5P)
```

Derivada:

```text
d pi / dP = -5(30-P) + (170-5P) - 5(P-5)
```

Simplificando:

```text
-150 + 5P + 170 - 5P - 5P + 25 = 0
45 - 5P = 0
P* = 9
```

Luego:

```text
F* = (30-9)^2/2 = 220.5
Q_1 = 21
Q_2 = 31
Q_T = 3*21 + 2*31 = 125
pi = 5*220.5 + (9-5)*125 = 1602.5
```

Interpretacion Whapi:

Una tarifa unica seria ofrecer un solo plan para todos. Funciona, pero deja dinero sobre la mesa: las empresas grandes podrian pagar mas y las pequenas podrian necesitar un plan mas limitado.

---

# 5. Menu de tarifas en dos partes

## 5.1 Estructura

```text
Plan bajo: T_1(Q) = F_1 + P_1 Q
Plan alto: T_2(Q) = F_2 + P_2 Q
```

Demandas:

```text
Q_1 = a_1 - P_1
Q_2 = a_2 - P_2
```

Excedentes:

```text
EC_1(P_1) = (a_1-P_1)^2 / 2
EC_2(P_2) = (a_2-P_2)^2 / 2
EC_2(P_1) = (a_2-P_1)^2 / 2
```

Participacion del bajo:

```text
F_1 = EC_1(P_1)
```

Autoseleccion del alto:

```text
EC_2(P_2) - F_2 = EC_2(P_1) - F_1
```

Despejando:

```text
F_2 = EC_2(P_2) - EC_2(P_1) + F_1
```

Resultado usual:

```text
P_2 = c
P_1 > c
```

Lectura:

- El tipo alto consume cantidad eficiente.
- El tipo bajo recibe una distorsion: su precio por unidad queda por sobre costo marginal.
- Esa distorsion hace menos atractivo el plan barato para el tipo alto.

## 5.2 Caso tipo control: gimnasio

Datos:

```text
Q_1 = 30 - P
Q_2 = 54 - P
c = 10
n_1 = 3
n_2 = 1
```

Tarifa unica segun pauta:

```text
P = 16
F = 98
pi = 872
```

Menu de planes:

1. Para el alto:

```text
P_2 = c = 10
Q_2 = 54 - 10 = 44
```

2. Para el bajo, se busca `P_1 > 10` para reducir la tentacion del alto de comprar plan bajo.

3. Cargo fijo bajo:

```text
F_1 = EC_1(P_1) = (30-P_1)^2/2
```

4. Cargo fijo alto:

```text
F_2 = EC_2(10) - EC_2(P_1) + F_1
```

5. Beneficio:

```text
pi = n_1F_1 + n_2F_2 + n_1(P_1-c)(30-P_1)
```

porque `P_2 = c`, entonces el margen variable del alto es cero y se extrae valor por `F_2`.

## 5.3 Pregunta tipica

Pregunta: Por que el plan bajo se distorsiona?

Respuesta modelo:

El plan bajo se distorsiona para relajar la restriccion de autoseleccion del tipo alto. Si el plan bajo fuera demasiado atractivo, el tipo alto preferiria imitar al bajo y pagar menos. Por eso se reduce la calidad/cantidad del plan bajo o se eleva su precio por unidad. Asi el tipo alto prefiere su propio plan y la empresa puede cobrarle un cargo fijo mayor.

---

# 6. Caso Whapi: discriminacion tipo 2 con planes Starter, Plus y Pro

## 6.1 Benchmarks SaaS usados

Datos de la carpeta:

```text
saas-market-2026.csv: 331 productos, 28 categorias
category-benchmarks-2026.csv: precios medianos por categoria
```

Categorias relevantes:

| Categoria | Herramientas | Precio mediano USD | % con plan gratis |
|---|---:|---:|---:|
| CRM | 18 | 32 | 39% |
| Email marketing | 20 | 19.95 | 70% |
| AI agents | 8 | 19.99 | 88% |
| AI assistants | 7 | 39 | 86% |
| LLM | 25 | 20 | 80% |
| Cloud hosting | 21 | 5.99 | 52% |

Lectura:

- Un SaaS simple de infraestructura puede partir bajo.
- CRM y asistentes IA justifican tickets mas altos.
- Whapi combina CRM + WhatsApp + IA + pagos + analytics, entonces debe ubicarse por sobre una herramienta simple, pero con entrada accesible para pequenas empresas.

## 6.2 Segmentos

| Tipo | Cliente | Necesidad | Sensibilidad al precio |
|---|---|---|---|
| Bajo | Negocio pequeno | Responder WhatsApp y no perder leads | Alta |
| Medio | Equipo comercial | CRM, seguimiento, catalogo, pagos | Media |
| Alto | WhatsApp como canal principal | Automatizacion, analitica, integraciones, soporte | Baja |

## 6.3 Menu didactico de planes

Este menu es para estudiar microeconomia, no precio final productivo.

| Plan | Tipo objetivo | Pago mensual `F` | Uso incluido `Q` | Precio extra `P` |
|---|---|---:|---:|---:|
| Starter | Bajo | 19 USD | 300 conversaciones | Alto por exceso |
| Plus | Medio | 49 USD | 1.500 conversaciones | Medio por exceso |
| Pro | Alto | 99 USD | 5.000 conversaciones | Bajo por exceso |

Interpretacion economica:

- Starter debe ser util, pero no tan conveniente para empresas grandes.
- Plus agrega CRM, pagos, memoria y seguimiento.
- Pro agrega integraciones, analytics, mayor capacidad y soporte.

Si Pro no tuviera beneficios reales, el cliente alto se podria "colar" en Plus o Starter.

## 6.4 Formulacion con demanda

Supongamos demandas por uso:

```text
Q_b = 800 - 20P_b
Q_m = 2500 - 25P_m
Q_a = 6000 - 30P_a
```

Donde `P_i` es precio por conversacion extra o precio implicito de uso.

Valor del cliente:

```text
V_i(Q) = integral_0^Q P_i(q)dq
```

Si la demanda inversa es:

```text
P_i = a_i - b_iQ
```

entonces:

```text
V_i(Q) = a_iQ - (b_iQ^2)/2
```

Pago total:

```text
T_i = F_i + P_i Q_i
```

Utilidad:

```text
U_i = V_i(Q_i) - T_i
```

## 6.5 Restricciones de participacion

Cada tipo debe preferir comprar antes que no comprar:

```text
V_b(Q_b) - T_b >= 0
V_m(Q_m) - T_m >= 0
V_a(Q_a) - T_a >= 0
```

En lenguaje Whapi:

- Starter se compra si el valor de recuperar ventas supera el pago.
- Plus se compra si el valor del seguimiento comercial supera el pago.
- Pro se compra si la automatizacion y escala justifican el pago.

## 6.6 Restricciones de compatibilidad de incentivos

Cada tipo debe preferir su plan:

```text
U_b(Starter) >= U_b(Plus)
U_m(Plus) >= U_m(Starter)
U_m(Plus) >= U_m(Pro)
U_a(Pro) >= U_a(Plus)
U_a(Pro) >= U_a(Starter)
```

Traduccion:

- Una empresa pequena no debe sentirse forzada a Pro.
- Una empresa mediana debe ver Plus como el mejor balance.
- Una empresa grande debe preferir Pro porque Starter o Plus le quedan caros en exceso, limitados o incomodos.

## 6.7 Renta informativa

La renta informativa es el excedente que se le deja al tipo alto para que no imite al bajo.

```text
RI_a = V_a(Q_b) - T_b
```

O en tarifa en dos partes:

```text
RI_a = EC_a(P_b) - F_b
```

Interpretacion Whapi:

El cliente grande podria obtener bastante valor incluso usando un plan barato. Para evitar que lo haga, el plan barato debe tener limites reales: conversaciones, usuarios, integraciones, analytics, SLA o automatizaciones.

## 6.8 Respuesta modelo para examen usando Whapi

Pregunta: Explique como Whapi puede usar discriminacion de precios de segundo grado.

Respuesta:

Whapi puede ofrecer un menu de planes Starter, Plus y Pro para que los clientes se autoseleccionen segun su intensidad de uso y disposicion a pagar. Como Whapi no observa perfectamente cuanto valora cada empresa la automatizacion de WhatsApp, disena planes con distintos cargos fijos, limites de conversaciones, integraciones y soporte. El plan bajo debe satisfacer la restriccion de participacion del cliente pequeno, mientras que el plan alto debe cumplir compatibilidad de incentivos: una empresa grande debe preferir Pro antes que imitar Starter. Para lograrlo, el plan bajo suele estar distorsionado con menor capacidad o mayor precio por uso extra. El tipo alto recibe renta informativa, porque se le debe dejar algun excedente para que elija su propio plan.

---

# 7. Ventas atadas y paquetes

## 7.1 Venta atada

La empresa obliga a comprar un producto junto con otro.

```text
V_A + V_B >= P_pack
```

Caso Whapi:

Vender IA + CRM + pagos como un paquete obligatorio.

## 7.2 Paquete puro

Solo se vende el paquete.

```text
pi = (P_pack - C_A - C_B)N(P_pack)
```

## 7.3 Paquete mixto

Se venden productos separados y tambien paquete:

```text
U_A = V_A - P_A
U_B = V_B - P_B
U_AB = V_A + V_B - P_AB
```

Caso Whapi:

- WhatsApp automation solo.
- CRM solo.
- Pack WhatsApp + CRM + pagos + IA.

Conviene empaquetar cuando las valoraciones son diferentes entre clientes y el paquete permite capturar mas disposicion a pagar.

---

# 8. Cournot

## 8.1 Concepto

Las empresas compiten en cantidades simultaneamente.

```text
P = A - BQ
Q = q_1 + q_2
P = A - B(q_1+q_2)
```

Beneficio empresa 1:

```text
pi_1 = [A - B(q_1+q_2)]q_1 - CT_1(q_1)
```

Beneficio empresa 2:

```text
pi_2 = [A - B(q_1+q_2)]q_2 - CT_2(q_2)
```

Condicion:

```text
IMg_i = CMg_i
```

## 8.2 Reacciones con costos lineales

Si:

```text
CT_1 = c_1q_1
CT_2 = c_2q_2
```

entonces:

```text
q_1 = (A - c_1 - Bq_2)/(2B)
q_2 = (A - c_2 - Bq_1)/(2B)
```

## 8.3 Ejercicio resuelto

Datos:

```text
P = 100 - Q
Q = q_1 + q_2
CT_1 = 10q_1
CT_2 = 10q_2
```

Empresa 1:

```text
pi_1 = (100 - q_1 - q_2)q_1 - 10q_1
pi_1 = 90q_1 - q_1^2 - q_1q_2
d pi_1/dq_1 = 90 - 2q_1 - q_2 = 0
q_1 = (90 - q_2)/2
```

Empresa 2:

```text
q_2 = (90 - q_1)/2
```

Por simetria:

```text
q_1 = q_2
q = (90 - q)/2
2q = 90 - q
3q = 90
q = 30
```

Resultado:

```text
q_1 = 30
q_2 = 30
Q = 60
P = 40
pi_1 = (40-10)30 = 900
pi_2 = 900
```

Caso Whapi:

Si Whapi compite con otro CRM de WhatsApp en capacidad o cantidad de clientes atendidos, cada firma anticipa que si produce/vende mas, baja el precio de mercado.

---

# 9. Competencia perfecta y suma de costos marginales

## 9.1 Regla

```text
P = CMg_i(q_i)
```

Para varias firmas:

```text
P = CMg_1(q_1)
P = CMg_2(q_2)
Q^S(P) = q_1(P) + q_2(P)
```

Equilibrio:

```text
Q^D(P) = Q^S(P)
```

## 9.2 Ejemplo

Si:

```text
CMg_1 = 200 + 2q_1
CMg_2 = 100 + 4q_2
```

Entonces:

```text
q_1 = (P-200)/2
q_2 = (P-100)/4
```

Oferta agregada:

```text
Q^S = (P-200)/2 + (P-100)/4
```

Paso clave: solo incluir cantidades positivas. Si el precio es menor que el intercepto de una firma, esa firma produce cero.

---

# 10. Costo social de Cournot

## 10.1 Formula

```text
CS = 1/2 * (Q_CP - Q_C) * (P_C - CMgAgregado(Q_C))
```

Transferencia de consumidores a productores:

```text
TR = (P_C - P_CP)Q_C
```

Diferencia:

- Transferencia: no desaparece, cambia de manos.
- Perdida social: bienestar que se pierde para todos.

Respuesta modelo:

En Cournot las firmas restringen cantidad para elevar precio. Esto genera transferencia desde consumidores hacia productores y, ademas, una perdida social por unidades que no se producen aunque su valor para consumidores era mayor que su costo marginal.

---

# 11. Bertrand

## 11.1 Concepto

Las empresas compiten en precios.

Con bienes homogeneos y costos marginales constantes iguales:

```text
P = CMg = c
pi = 0
```

Lectura:

- Si una empresa cobra un poco menos, se queda con todo el mercado.
- La competencia en precios empuja el precio al costo marginal.

Comparacion:

| Modelo | Variable estrategica | Resultado tipico |
|---|---|---|
| Cournot | Cantidad | Precio sobre costo marginal |
| Bertrand | Precio | Precio igual a costo marginal si bienes homogeneos |
| Stackelberg | Cantidad secuencial | Lider suele producir mas |

Caso Whapi:

Si todos los SaaS de WhatsApp fueran identicos, la competencia en precios seria brutal. Whapi evita Bertrand puro diferenciandose con IA, CRM, pagos, integraciones y experiencia.

---

# 12. Stackelberg

## 12.1 Concepto

Juego secuencial: una empresa lider decide primero y la seguidora responde despues.

Se resuelve por induccion hacia atras:

1. Resolver la reaccion de la seguidora.
2. Sustituir esa reaccion en el problema de la lider.
3. Maximizar beneficio de la lider.
4. Calcular cantidades, precio y beneficios.

## 12.2 Ejemplo

Datos:

```text
P = 100 - q_1 - q_2
CT_1 = 10q_1
CT_2 = 10q_2
```

Seguidora:

```text
pi_2 = (100-q_1-q_2)q_2 - 10q_2
pi_2 = 90q_2 - q_1q_2 - q_2^2
d pi_2/dq_2 = 90 - q_1 - 2q_2 = 0
q_2 = (90 - q_1)/2
```

Lider sustituye:

```text
P = 100 - q_1 - (90-q_1)/2
P = 55 - q_1/2
```

Beneficio lider:

```text
pi_1 = (P-10)q_1
pi_1 = (45 - q_1/2)q_1
pi_1 = 45q_1 - q_1^2/2
d pi_1/dq_1 = 45 - q_1 = 0
q_1 = 45
```

Seguidora:

```text
q_2 = (90-45)/2 = 22.5
Q = 67.5
P = 32.5
```

Interpretacion:

La lider se compromete a producir mas, dejando menos espacio rentable para la seguidora.

---

# 13. Teoria de juegos

## 13.1 Elementos

Un juego tiene:

- Jugadores.
- Estrategias.
- Pagos.
- Informacion.
- Tiempo: simultaneo o secuencial.

## 13.2 Mejor respuesta

Una estrategia es mejor respuesta si da el mayor pago dada la estrategia del rival.

```text
u_i(s_i, s_j) >= u_i(s_i', s_j)
```

## 13.3 Nash

Equilibrio de Nash:

```text
s_i* = BR_i(s_j*)
s_j* = BR_j(s_i*)
```

Nadie quiere desviarse unilateralmente.

## 13.4 Estrategia dominante

Una estrategia es dominante si es mejor sin importar lo que haga el rival.

## 13.5 Maximin

Procedimiento:

1. Para cada estrategia, mira el peor pago posible.
2. Elige la estrategia cuyo peor pago sea el mayor.

```text
max[min(u_i)]
```

## 13.6 Dilema del prisionero

| | B colude | B compite |
|---|---:|---:|
| A colude | 50,50 | 0,80 |
| A compite | 80,0 | 20,20 |

Equilibrio de Nash:

```text
(Competir, Competir)
```

Optimo conjunto:

```text
(Coludir, Coludir)
```

Explicacion:

Aunque ambos estarian mejor coludiendo, cada uno tiene incentivo individual a competir si el otro colude. Por eso la estrategia dominante es competir.

Caso Whapi:

Dos SaaS podrian estar mejor manteniendo precios altos, pero cada uno tiene incentivo a bajar precio para captar clientes. En un juego repetido, la cooperacion tacita puede sostenerse si el castigo futuro por desviarse es suficientemente grande.

---

# 14. Preguntas probables y respuestas modelo

## 14.1 Discriminacion tipo 2

Pregunta: Que es discriminacion de segundo grado?

Respuesta: Es una estrategia donde la empresa no observa directamente el tipo de consumidor, por lo que ofrece un menu de precios, cantidades o calidades para que los consumidores se autoseleccionen. El objetivo es capturar mas excedente respetando participacion y compatibilidad de incentivos.

Pregunta: Que es la renta informativa?

Respuesta: Es el excedente que se deja al consumidor de tipo alto para que prefiera su propio plan y no imite al tipo bajo. Surge porque la empresa no puede identificar perfectamente el tipo de consumidor.

Pregunta: Por que el plan bajo se distorsiona?

Respuesta: Porque si el plan bajo fuera demasiado atractivo, el tipo alto lo elegiria para pagar menos. La empresa reduce cantidad/calidad o sube precio por unidad del plan bajo para mantener la autoseleccion.

## 14.2 Tarifa en dos partes

Pregunta: Por que el cargo fijo se iguala al excedente del consumidor bajo?

Respuesta: Porque en una tarifa unica la empresa quiere que tambien participe el tipo bajo. Si el cargo fijo fuera mayor que su excedente, el tipo bajo no compraria. Por eso el maximo cargo fijo compatible con su participacion es `F = EC_bajo`.

Pregunta: Por que en el menu suele cumplirse `P_alto = CMg`?

Respuesta: Porque para el tipo alto no conviene distorsionar la cantidad. La empresa extrae valor principalmente mediante el cargo fijo. La distorsion se aplica al tipo bajo para evitar imitacion.

## 14.3 Cournot

Pregunta: Como se resuelve Cournot?

Respuesta: Se escribe el beneficio de cada firma en funcion de su cantidad y la cantidad rival. Luego se deriva respecto a la cantidad propia, se obtiene la funcion de reaccion de cada empresa y se resuelve el sistema. Finalmente se calcula precio, cantidad total y utilidades.

Pregunta: Por que Cournot genera perdida social?

Respuesta: Porque las empresas restringen cantidad para elevar precio por sobre costo marginal. Al producir menos que competencia perfecta, quedan unidades sin producir cuyo valor para consumidores era mayor que su costo.

## 14.4 Bertrand

Pregunta: Por que Bertrand puede llegar al resultado competitivo?

Respuesta: Porque si los productos son homogeneos y los costos iguales, cualquier empresa puede capturar el mercado bajando apenas el precio. Esa presion continua hasta que el precio iguala el costo marginal.

## 14.5 Stackelberg

Pregunta: Por que Stackelberg se resuelve por induccion hacia atras?

Respuesta: Porque la lider decide anticipando la reaccion futura de la seguidora. Primero se calcula como respondera la seguidora, luego la lider incorpora esa reaccion en su propia maximizacion.

## 14.6 Juegos

Pregunta: Que es equilibrio de Nash?

Respuesta: Es una combinacion de estrategias donde ningun jugador quiere desviarse unilateralmente, dado lo que hace el otro.

Pregunta: Diferencia entre Nash y optimo conjunto.

Respuesta: Nash es estabilidad individual; optimo conjunto maximiza pagos totales. En el dilema del prisionero, pueden no coincidir.

---

# 15. Checklist final antes de dormir

## Debo saber calcular

- `EC = (a-P)^2/2`.
- Beneficio `pi = P(Q)Q - CT(Q)`.
- Tarifa en dos partes `T(Q)=F+PQ`.
- Cargo fijo `F = EC_bajo`.
- Restricciones `IR` e `IC`.
- Renta informativa.
- Funciones de reaccion en Cournot.
- Equilibrio competitivo con `P=CMg`.
- Perdida social.
- Nash, dominante y maximin.

## Debo saber explicar

- Por que discriminar precios requiere poder de mercado.
- Por que el tipo alto recibe renta informativa.
- Por que el plan bajo se distorsiona.
- Por que Cournot produce menos que competencia perfecta.
- Por que Bertrand puede llevar a `P=CMg`.
- Por que Stackelberg favorece al lider.
- Por que el dilema del prisionero termina en un resultado individualmente estable pero colectivamente peor.

## Mini speech para recordar todo

Whapi quiere cobrar distinto a clientes distintos, pero no sabe perfectamente cuanto vale cada uno. Entonces disena Starter, Plus y Pro para que cada empresa se autoseleccione. Starter debe atraer al pequeno, pero tener limites para que el grande no lo imite. Pro debe entregar valor real al grande para justificar mayor pago. Eso es discriminacion tipo 2: participacion, autoseleccion y renta informativa. La misma logica aparece en tarifa en dos partes: un cargo fijo captura excedente y un precio por uso controla cantidad. En mercados con competidores, Whapi ya no decide sola: si compite en cantidades se parece a Cournot, si compite en precios se parece a Bertrand, si se mueve primero y otros responden se parece a Stackelberg. Y si los competidores deciden si bajar precios o mantenerlos, aparece teoria de juegos y dilema del prisionero.

---

# 16. Orden recomendado de repaso

1. Tarifa en dos partes.
2. Discriminacion tipo 2 y menu de planes.
3. Excedente, bienestar y perdida social.
4. Cournot.
5. Competencia perfecta y suma de costos marginales.
6. Bertrand y Stackelberg.
7. Teoria de juegos.
8. Caso Whapi completo para explicar en palabras.

Si queda poco tiempo, prioriza:

```text
EC = (a-P)^2/2
T(Q) = F + PQ
IR: V_i(Q_i) - T_i >= 0
IC: U_i(plan propio) >= U_i(plan ajeno)
Cournot: IMg_i = CMg_i
Competencia perfecta: P = CMg
Nash: nadie quiere desviarse solo
```
