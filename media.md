# Multimedia

Anki almacena los sonidos e imágenes utilizadas en sus notas en una carpeta junto a
la colección. Para obtener más información sobre la ubicación de la carpeta, consulte la sección [ubicación 
de los archivos](files.md). Cuando agrega archivos multimedia dentro de Anki, ya sea por
usando el icono de clip en el [editor](editing.md) o pegándolo en
un campo, Anki lo copiará de su ubicación original en los archivos multimedia
carpeta. Esto facilita hacer copias de seguridad de los archivos multimedia de su colección o moverlos
a otra computadora.

Puede usar la opción de menú _Herramientas y Verificar multimieda_ para escanear sus notas y
carpeta multimedia. Generará un informe de archivos en la carpeta multimedia
que no son utilizados por ninguna nota, y archivos referenciados en notas pero
faltantes ensu carpeta de marchivos multimedia. No escanea preguntas o respuestas
en las plantillas, por lo que no puede colocar referencias de archivos multimedia a campos en
la plantilla. Si necesita una imagen o sonido estático en cada tarjeta, asígnele un nombre
con un guón bajo inicial \_ p.e. '\_perro.jpg') para decirle a Anki que lo ignore cuando
buscando archivos multimedia. Si elimina archivos multimedia usando la verificación de archivos multimedia no utilizados,
Anki lo moverá a la carpeta de la papelera de su sistema operativo, para que pueda
recuperar si elimina accidentalmente archivos multimedia que no deberían haber sido
eliminados.

Anki usa un programa llamado mplayer para soportar sonidos y
videos. Se admite una amplia variedad de formatos de archivo, pero no todos
los formatos funcionarán en AnkiWeb y los clientes móviles. Audio MP3 y
El video MP4 parece ser el más universalmente compatible.