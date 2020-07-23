# Buscando

La pantalla de exploración de Anki y la función de cubierta filtrada utilizan un método común
de búsqueda de tarjetas/notas específicas.

## Búsquedas simples

Cuando escribe texto en el cuadro de búsqueda, Anki encuentra notas coincidentes
y muestra sus cartas. Anki busca en todos los campos de las notas, pero
no busca etiquetas (consulte más adelante en esta sección cómo buscar
para etiquetas). Algunos ejemplos:

`perro`
buscar "perro": también coincidirá con palabras como "perros" y "perroflauta".

`perro gato`
encuentra notas que tienen tanto "perro" como "gato", como "lloviendo
gatos y perros".

`perro or gato`
encuentra notas con "perro" o "gato". 

`perro (gato or ratón)`
encuentra notas con perro y gato, o perro y ratón.

`-gato`
encuentra notas sin la palabra "gato".

`-gato -ratón`
no encuentra notas ni con "gato" ni con "ratón".

`-(gato or ratón)`
igual que el anterior.

`"un perro"`
encuentra notas con la secuencia exacta de caracteres "un perro" en ellos, como
como "aun perro", pero no como "unperro" o "perro un".

`-"un perro"`
encuentra notas sin la frase exacta "un perro".

`p_rro`
encuentra notas con p, una letra, y "rro", como parro, perro, purro, etc.

`p*rro`
encuentra notas con p, cero o más letras, y"rro", como prro, perro, puerro, patarro
etc.

`w:perro`
buscar "perro" en el límite de una palabra: coincidirá con "perro", pero no con "perros"
o "perroflauta". Requiere Anki 2.1.24+ o AnkiMobile 2.1.61+.

`w:perro*`
coincidirá con "perro" y "perros" y "perroflauta", pero no con "enperro".

`w:*perro`
coincidirá con "perro" y "enperro", pero no con "perros" y "perroflauta".


Cosas a tener en cuenta de lo anterior:

- Los términos de búsqueda están separados por espacios.

- Cuando se proporcionan varios términos de búsqueda, Anki busca notas que
  coincide con todos los términos: se inserta un 'y' implícito entre cada
  término. En Anki 2.1.24+ y AnkiMobile 2.0.60+ puedes ser explícito
  si lo desea ("perro and gato" (and es "y" en inglés) es lo mismo que "perro gato"), pero versiones más
  antiguas de Anki tratarán "and" como una palabra más para buscar.

- Puede usar "or" ("o") si solo necesita uno de los términos para que coincida.

- Puede anteponer un signo de negación ("-") a un término para buscar notas que no
  partido.

- Si desea buscar algo, incluido un espacio o
  paréntesis, debe de ir entre comillas dobles ("). Puedes citar cualquiera de los
  `"la palabra: entera"`, o simplemente la `parte:"despúes de punto y coma"`.

- Puede agrupar los términos de búsqueda colocándolos entre paréntesis, como en el
  ejemplo de **perro (gato or ratón)**. Esto se vuelve importante cuando
  combina búsquedas OR y AND - en el ejemplo, con el
  paréntesis, coincide con 'perro gato' o 'perro ratón', mientras que
  sin ellos, coincidiría con 'perro y gato' o 'ratón'.

- Anki solo puede buscar dentro del formato en [campo de clasificación](editing.md#customizing-fields) que ha configurado. Por ejemplo, si agrega
  "**ej**emplo" a uno de sus campos, esto no se igualará cuando
  busque "ejemplo" a menos que ese campo sea el campo de clasificación. Si una
  palabra no está formateada o el formato no cambia en la
  a mitad de la palabra, entonces Anki podrá encontrarlo en cualquier campo.
  
## Limitando a un campo

También puede pedirle a Anki que coincida solo si un campo en particular contiene
texto. A diferencia de las búsquedas anteriores, la búsqueda en los campos requiere un "exacto
partido 'por defecto.

`front:perro`
encuentra notas con un campo frontal de exactamente "perro". Un campo que dice "a
perro "no coincidirá.

`front:*perro*`
encuentra notas con el campo frontal que contiene perro en algún lugar-

`front:`
encuentra notas que tengan un campo frontal vacío.

`front:_*`
encuentra notas que tengan un campo frontal no vacío.

`front:*`
encuentra notas que tengan un campo frontal, vacío o no

`fr*:text`
encuentra notas en un campo que comience con "fr". Requiere Anki 2.1.24+ o AnkiMobile 2.1.60+.

## Etiquetas, mazos, tarjetas y notas

`tag:animal`
encuentra notas con la etiqueta "animal".

`tag:none`
encuentra notas sin etiquetas.

`tag:ani*`
encuentra notas con etiquetas que comienzan con "ani".

`deck:francés`
encuentra tarjetas en el mazo "francés", o submazos como "francés::Vocabulario".

`deck:francés -deck:francés::*`
encuentra tarjetas en el mazo francés, pero no en ninguno de sus submazos.

`deck:"vocabulario francés"`
encuentra cuando un mazo tiene un espacio en el nombre.

`"deck:vocabulario francés"`
otra opción válida para el caso anterior.

`deck:filtered` 
mazos filtrados solamente.

`-deck:filtered` 
mazos normales solamente.

`card:forward`
buscar tarjetas de tipo "forward".

`card:1`
buscar tarjetas por número de plantilla, por ejemplo, para encontrar la segunda pregunta anidada
de una nota, usaría la card:2.

`note:Básico`
encuentra tarjetas con un tipo de nota Básica.

## Ignorando acentos / combinando caracteres

Requiere Anki 2.1.24+ o AnkiMobile 2.0.60+.

Puede usar `nc:` para eliminar los caracteres combinados ("sin combinación"). Por ejemplo:

`nc:básico`
hace conicidir las notas con "basico", "básico", etc.

`nc:uber`
hace coincidir las notas con "uber", "über", "Über", etc.

`nc:は`
coincide con "は", "ば" y "ぱ".

Las búsquedas que ignoran la combinación de caracteres son más lentas que las búsquedas normales.

## Expresiones regulares

Anki 2.1.24+ y AnkiMobile 2.0.60+ admiten búsquedas en notas con "expresiones regulares",
Una forma estándar y poderosa de búsqueda en texto.

Inicie una búsqueda con `re:` para buscar por expresión regular. Algunos ejemplos:

`"re:(algún|otro).*cosa"`
encuentra notas que tengan "algún" u "otro", seguidos de 0 o más caracteres, y luego "cosa".

`re:\d{3}`
encontraa notas que tienen 3 dígitos consecutivos.

Las expresiones regulares también se pueden limitar a un campo específico. Tenga en cuenta que a diferencia de las búsquedas normales
en un campo específico, las expresiones regulares en los campos no requieren una coincidencia exacta. P.ej:

`front:re:[a-c]1`
coincide con mayúsculas o minúsculas a1, B1 o c1 que se produce en cualquier parte del campo "Front".

`front:re:^[a-c]1$`
como el caso anterior, pero no coincidirá si algún otro texto se situa antes o después de a1/b1/c1.

Puede obtener más información sobre las expresiones regulares aquí: https://regexone.com/lesson/introduction_abcs

Algunas cosas a tener en cuenta:

- La búsqueda no distingue entre mayúsculas y minúsculas por defecto; use (? -i) al comienzo para activar la distinción entre mayúsculas y minúsculas.
- Algunos textos, como espacios y líneas nuevas, pueden representarse de manera diferente en HTML; puede
   usar el editor HTML en la pantalla de edición para ver el contenido HTML subyacente.
- Para los detalles del soporte de expresiones regulares de Anki, consulte la documentación de la caja de expresiones regulares: https://docs.rs/regex/1.3.9/regex/#syntax


## Estado de la tarjeta

`is:due`
Revisar tarjetas y tarjetas de aprendizaje esperando ser estudiadas.

`is:new`
tarjetas nuevas.

`is:learn`
tarjetas en aprendizaje.

`is:review`
revisiones (tanto vencidas como no vencidas) y tarjetas caducadas.

`is:suspended`
tarjetas que han sido suspendidas manualmente.

`is:buried`
tarjetas que han sido enterradas, ya sea [automáticamente](study.md#siblings-and-enterying) o
manialmente.

Las tarjetas que han caducado caen en varias de estas categorías, por lo que puede
sea ​​útil combinarlas para obtener resultados más precisos:

`is:learn is:review`
tarjetas que han caducado y están esperando volver a aprender.

`-is:learn is:review`
tarjetas de revisión, sin incluir las tarjetas caducadas.

`is:learn -is:review`
tarjetas que se están aprendiendo por primera vez.


## Propiedades de la tarjeta

`prop:ivl>=10`
tarjetas cuyo intervalo es de 10 días o más.

`prop:due=1`
tarjetas para revisar mañana.

`prop:due=-1`
tarjetas que vencen ayer y que aún no han sido respondidas.

`prop:due>-1 prop:due<1`
tarjetas de vencimiento entre ayer y mañana.

`prop:reps<10`
tarjetas que han sido respondidas menos de 10 veces.

`prop:lapses>3`
tarjetas que han pasado al reaprendizaje más de 3 veces.

`prop:ease!=2.5`
tarjetas más fáciles o más difíciles que las predeterminadas.

Tenga en cuenta que "due" solo coincide con las tarjetas de revisión y las tarjetas de aprendizaje con un
intervalo de un día o más: tarjetas en el aprendizaje con pequeños intervalos como
10 minutos no están incluidas.

## Recientemente añadido

`added:1`
tarjetas añadidas hoy.

`added:7`
tarjetas añadidas la semana pasada.

La verificación se realiza contra el tiempo de creación de la tarjeta en lugar del de la creación de notas
por lo que las tarjetas que se generaron dentro del marco de tiempo serán
incluidas incluso si sus notas se agregaron hace mucho tiempo.

## Recientemente contestado

`rated:1`
tarjetas contestadas hoy.

`rated:1:2`
tarjetas contestadas difícil (2) hoy.

`rated:7:1`
tarjetas respondidas de nuevo (1) en los últimos 7 días.

`rated:31:4`
tarjetas respondidas fácil (4) en el último mes.

Por eficiencia, las búsquedas de calificación están limitadas a 31 días.

## ID de objeto

`nid:123`
todas las tarjetas de la nota con nota ID 123.

`cid:123`
la tarjeta con ID de tarjeta 123.

`mid:123`
encontrar tipos de notas con el ID de tipo de nota 123.

Las notas y las ID de las tarjetas se pueden encontrar en el cuadro de diálogo [información de la tarjeta](stats.md) en el
navegador. Los ID de tipo de nota se pueden encontrar haciendo clic en un tipo de nota en el
explorador. Estas búsquedas también pueden ser útiles al hacer desarollo de 
complementos o de otra manera trabajando estrechamente con la base de datos.

Los ID de objeto no funcionarán en los clientes móviles y no están destinados a
ser utilizado en mazos filtrados en este momento.