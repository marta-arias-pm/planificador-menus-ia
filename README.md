# Planificador de menús semanales asistido por IA

**El inventario de la nevera entra; salen cuatro documentos: el menú de la semana, la lista de la compra, el plan de batch cooking y la preparación de cada noche.**

> Este caso describe el sistema, no a las personas que lo usan. No incluye datos personales, de salud ni de los miembros del hogar.

---

## El problema

Planificar la comida de una semana en un hogar con restricciones alimentarias y comensales con necesidades distintas no es un problema de recetas: es un problema de restricciones.

Cada semana hay que cruzar cuatro cosas que cambian: qué hay en casa, qué puede comer cada persona, cuánto tiempo real habrá el fin de semana para cocinar, y qué aguanta un tupper hasta el día siguiente.

Hacerlo a mano cuesta una tarde. Y como cuesta una tarde, no se hace: se improvisa entre semana, se cocina a diario y se compra de más.

## Qué construí

Un sistema con tres piezas:

**Base de conocimiento estable.** Recetas digitalizadas, una guía de nutrición y la composición del hogar con sus restricciones. Se carga una vez y no hay que repetirla cada semana.

**Entrada semanal variable.** Jueves o viernes indico dos cosas: qué hay en el congelador y la nevera, y cuánto tiempo tengo disponible el fin de semana.

**Salida fija.** Siempre los mismos cuatro documentos, listos para usar sin interpretarlos.

## El contrato de salida

Lo que convierte esto en un sistema, y no en una consulta suelta, es que cada entregable tiene un destinatario y un momento distintos:

| Documento | Para quién | Cuándo |
|---|---|---|
| Menú de la semana | Toda la casa | Pegado en la cocina, consulta diaria |
| Lista de la compra | Quien va a comprar | Organizada y con cantidades |
| Plan de batch cooking | Quien cocina el fin de semana | Ajustado al tiempo real disponible |
| Preparación de cada noche | Quien prepara los tuppers | La noche anterior, en pocos minutos |

Un único documento largo con todo dentro habría obligado a buscar la información cada vez. Cuatro documentos cortos, cada uno para un momento concreto, se usan.

## Las decisiones de diseño que importaron

**El inventario va primero.** El menú se construye desde lo que ya hay en casa, no al revés. Eso reduce desperdicio y compra, y es también la restricción que hace útil la propuesta.

**El tiempo disponible es una entrada, no un supuesto.** Un plan de batch cooking que asume un sábado entero libre no sirve ningún sábado real. Al declarar el tiempo disponible, el plan se ajusta a él.

**Lo estable vive en la base; lo que cambia, en la petición.** Las restricciones y las recetas no se repiten cada semana. Solo entran el inventario y el tiempo. Esa separación es lo que permite que el sistema siga funcionando semana tras semana sin volverse pesado.

**Previsibilidad por encima de creatividad.** Las mismas cuatro salidas, con el mismo formato, siempre. Un sistema doméstico que cada semana entrega algo distinto obliga a aprenderlo de nuevo cada vez, y se abandona.

## Resultado

- La planificación semanal pasó de ocupar una tarde a una petición de unos minutos.
- Entre semana se cocina mucho menos: el trabajo pesado está concentrado y planificado.
- El objetivo real no era ahorrar tiempo de cocina, sino recuperar tiempo en familia. Esa es la métrica por la que juzgo si el sistema funciona.

## Qué aprendí, aplicable fuera de casa

- Un asistente deja de ser un chat y se convierte en un sistema cuando tiene conocimiento persistente, entradas definidas y un contrato de salida fijo.
- Diseñar la salida pensando en quién la lee y en qué momento la lee es la mitad del trabajo. La otra mitad es no entregar de más.
- Separar lo estable de lo variable es lo que decide si una automatización sobrevive al tercer mes.

## Por qué publico esto

Es el caso que mejor muestra cómo trabajo con IA: no como una herramienta a la que se le piden cosas sueltas, sino como un sistema con entradas definidas, conocimiento estable y salidas que alguien puede usar directamente, sin tener que interpretarlas.
