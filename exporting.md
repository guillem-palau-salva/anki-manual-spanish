# Exportar

Exportar le permite guardar parte de su colección como un archivo de texto o
mazo de Anki empaquetado. Para exportar, haga clic en el menú Archivo y elija 'Exportar'.

## Archivos de texto

Si elige "Notas en texto plano", Anki escribirá el contenido del
notas en un archivo de texto. Cada campo está separado por un tabulador. Si edita
el archivo resultante y no modifia el primer campo, más tarde puede
importar ese archivo nuevamente en Anki y Anki actualizará sus notas en función de
sus ediciones, siempre que vuelva a importar en el mismo tipo de nota.

Si también necesita editar el primer campo,
necesita cambiar el formato de su tipo de nota para que el primer campo sea
un número de identificación en lugar del texto real. (Puede instalar el complemento "Add note id" ("Agregar ID de nota")
extensión para hacer este proceso más fácil).

Para que se conserve el formato cuando vuelva a importar texto,
el texto se exporta con todo el formato HTML incorporado.

## Mazos de Anki empaquetados

Un 'mazo empaquetado' consiste en cartas, notas, tipos de notas y cualquier sonido o
imágenes agrupadas en un archivo que termina con .apkg o .colpkg. Puede usar
mazos empaquetados para transferir tarjetas entre personas o para hacer copias de seguridad de piezas
de tu colección.

Hay dos tipos diferentes de mazos empaquetados.

### Colección (.colpkg)

Cuando exporta todas las cartas con la programación incluida, esto se denomina
'paquete de colección'. Anki copiará toda su colección en un archivo
terminando en .colpkg y lo colócará en su escritorio. Un paquete de colección es
usado para hacer una copia de seguridad de su colección o copiarla a otro dispositivo.

Los paquetes de colección creados con versiones anteriores de Anki se llamaron
collection.apkg.

Cuando este archivo se importe más tarde, Anki eliminará todas las tarjetas actuales
en la colección, reemplazando la colección con los elementos en el
archivo. Esto es útil para copiar su colección de un lado a otro entre
dispositivos.

Los archivos multimedia existentes en su colección no se eliminan cuando importa un
paquete de rcolección. Para eliminar archivos multimedia no utilizados, use _Herramientas_ y _Comprobar archivos multimedia_.

### Mazo (.apkg)

Los paquetes de mazo contienen un solo mazo (y cualquier mazo secundario que pueda tener).
Tienen un nombre de archivo que termina con .apkg, pero un nombre de archivo distinto de
collection.apkg. Cuando importe un paquete de mazo, Anki agregará el
contenido en su colección, en lugar de sobrescribir su colección.

Si se han importado previamente algunas notas en el paquete de mazo, Anki
mantendrá la versión con la hora de modificación más reciente. Así que si usted
descarga un mazo actualizado, las ediciones que se han realizado en él se actualizarán en
su colección, pero si vuelve a importar un
mazo sin cambios después de hacer ediciones en su colección, los cambios en
su colección se mantendrán.

Si elige no incluir información de programación, Anki asumirá
que está compartiendo el mazo con otras personas y eliminará tarjetas marcadas
y etiquetas de sanguijuela para que tengan una copia limpia.