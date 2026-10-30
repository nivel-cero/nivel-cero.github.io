---
title: "Primeros pasos"
weight: 20
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1"]
reviewed: 2026-10-30
---

Para que el DSpico abra tus juegos hay que preparar la microSD: tiene que estar en el formato correcto y
llevar los archivos de Pico Launcher (el menú del DSpico) y de Pico Loader (el que arranca los juegos). Si
tu cartucho ya funciona y solo quieres una versión nueva de Pico Launcher o de Pico Loader, ve a
[Actualizar](#actualizar).

## Qué necesitas

- El DSpico.
- Una microSD de marca y original, comprada en una tienda de confianza, porque se venden tarjetas falsas.
  El LNH Team no da un tamaño máximo, y en r/flashcarts hay quien usa el DSpico con tarjetas de 256 GB. Si
  tu cartucho vino con una tarjeta, mejor cámbiala: la guía de flashcarts.net dice que esas tarjetas
  suelen dejar de funcionar en cuestión de semanas, y que luego no se pueden recuperar sus archivos.
- Una computadora (un PC o un ordenador) en la que puedas meter la microSD, con un lector de tarjetas o un
  adaptador. No la formatees desde el celular, una tablet o un Chromebook: el tutorial de formateo de
  Sanrax dice que no son fiables para eso.

El cartucho no trae juegos. Los pones tú en la microSD, y en esta guía no se dice dónde conseguirlos.

No hace falta modificar ni «liberar» la consola. En una DS o una DS Lite, el cartucho funciona tal como
viene. En una DSi o una 3DS sin modificar, depende del firmware que lleve el cartucho, el programa grabado
en él: lo explica [Las dos variantes](firmware.md#las-dos-variantes).

## La microSD

La microSD tiene que estar en FAT32. Ningún programa del DSpico lee exFAT: con una tarjeta en exFAT, o sin
tarjeta, la consola no ve el cartucho o se queda colgada al encenderla. Las microSD de 64 GB o más vienen
de fábrica en exFAT, así que esas casi siempre hay que formatearlas.

Para saber en qué formato está la tuya, métela en la computadora:

- En Windows, abre el Explorador de archivos, haz clic derecho en la unidad de la microSD y elige
  «Propiedades». Mira qué dice en «Sistema de archivos».
- En Mac, selecciona la microSD en el Finder y elige «Archivo» > «Obtener información». Mira qué dice en
  «Formato».

Si dice FAT32, no hace falta formatearla. Si dice otra cosa, sigue los pasos de abajo para tu computadora.
Formatear borra todo lo que tiene la tarjeta: si guarda algo que quieras conservar, cópialo antes a la
computadora. Cuando termines, vuelve a mirar el formato: tiene que decir FAT32.

Las microSD de 2 GB o menos no se pueden dejar en FAT32 con los programas de esta página: quedan en FAT16
(en Windows sale «FAT»; en Mac, «MS-DOS (FAT16)»). No hemos probado si el DSpico las lee, así que mejor
usa una de 4 GB o más.

### Formatear en Windows

No uses la opción de formatear que trae Windows: la guía oficial del DSpico avisa de que no lo hagas, y
manda a una guía que usa sdFormatWindows. Estos son sus pasos:

1. Descarga
   [`sdFormatWindows.exe`](https://github.com/flashcarts/sdFormatWindows/releases/latest/download/sdFormatWindows.exe).
   El enlace descarga el archivo directamente.
2. Desconecta las memorias USB y los discos externos que tengas conectados, y mete la microSD en la
   computadora.
3. Abre `sdFormatWindows.exe` con doble clic. Si Windows avisa de que protegió tu PC, pulsa «Más
   información» y después «Ejecutar de todas formas». La guía de Sanrax cuenta que algunos antivirus lo
   marcan como peligroso porque pide permisos de administrador y no lleva firma digital, y que se le puede
   añadir una excepción. Hazlo solo con el archivo que descargaste del enlace del paso 1.
4. Cuando Windows pregunte si quieres permitir que haga cambios en el dispositivo, pulsa «Sí».
5. En «Select drive», elige la letra de la unidad de tu microSD. Si no aparece, pulsa «Refresh». Fíjate
   bien: si eliges otra, borras esa.
6. Mira la capacidad que pone en la tarjeta o en su caja, porque Windows la muestra menor: una de 64 GB
   sale como unos 59 GB. Si es de 64 GB o más, marca «Format as FAT32 (SDXC cards only)» y después «Force
   32KiB cluster size», que hasta entonces sale en gris. Si es de 32 GB o menos, no marques nada.
7. Pulsa «Format». Sale un aviso en inglés de que se borrará todo: pulsa «Sí» («Yes» si tu Windows está en
   inglés). Se abre una ventana negra con el progreso: no la cierres. Cuando salga «Format successful.»,
   pulsa «Aceptar» y cierra el programa.

### Formatear en Mac

1. Descarga
   [SD Card Formatter](https://www.sdcard.org/downloads/formatter/sd-memory-card-formatter-for-mac-download/),
   el programa de la SD Association. Esa página es una licencia en inglés: pulsa «Accept» y empezará la
   descarga. Abre el archivo descargado, «Install SD Card Formatter», y sigue el instalador.
2. Desconecta los discos externos que tengas conectados, mete la microSD en la computadora y abre SD Card
   Formatter.
3. En «Select Card», elige tu microSD. Fíjate bien: si eliges otro disco, borras ese.
4. Deja marcado «Quick Format» y pulsa «Format».
5. Si tu microSD es de 32 GB o menos, ya está. Si es de 64 GB o más, se queda en exFAT y falta un paso:
   1. Abre la Utilidad de Discos.
   2. En el menú «Visualización», elige «Mostrar todos los dispositivos».
   3. En la lista de la izquierda, elige la microSD entera, no el volumen que tiene dentro: la microSD es
      la línea de arriba, y el volumen va debajo, un poco más a la derecha.
   4. Pulsa «Borrar». En «Formato», elige «MS-DOS (FAT)»; en algunas versiones de macOS se llama
      «MS-DOS (FAT32)». En «Esquema», elige «Registro maestro de arranque». Si no aparece «Esquema»,
      cancela: elegiste el volumen y no la tarjeta.
   5. Pulsa «Borrar» y espera a que termine.

Con macOS 10.10 o anterior, la Utilidad de Discos es distinta y los pasos son otros: sigue el
[tutorial de formateo de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/formatting/) (en
inglés).

### Formatear en Linux

Sigue la parte de Linux del
[tutorial de formateo de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/formatting/) (en
inglés).

## Instalar Pico Launcher y Pico Loader

Los dos se instalan copiando archivos en la microSD. Se descargan de GitHub, de las páginas del LNH Team,
el grupo que diseña el DSpico.

1. Descarga
   [`Pico_Launcher.zip`](https://github.com/LNH-team/pico-launcher/releases/latest/download/Pico_Launcher.zip),
   la última versión de Pico Launcher.
2. Descarga
   [`Pico_Loader_DSPICO.zip`](https://github.com/LNH-team/pico-loader/releases/latest/download/Pico_Loader_DSPICO.zip),
   la última versión de Pico Loader para el DSpico. Pico Loader tiene un zip para cada cartucho: usa
   siempre el del DSpico, aunque tu cartucho se parezca a otro, porque sus autores avisan de que el de
   otro cartucho puede dañarlo.
3. Descomprime los dos zips: en Windows, clic derecho en el zip y «Extraer todo»; en Mac, doble clic.
   Cada uno queda en una carpeta con su nombre, `Pico_Launcher` y `Pico_Loader_DSPICO`. Esas dos carpetas
   no se copian a la microSD, solo lo que tienen dentro.
4. De `Pico_Launcher`, copia la carpeta `_pico` en la raíz de la microSD, es decir, fuera de cualquier
   carpeta.
5. Copia también `LAUNCHER.nds` en la raíz y cámbiale el nombre a `_picoboot.nds`, con el guion bajo
   delante. El cartucho arranca el archivo que tiene ese nombre. En Windows, si el archivo se ve como
   `LAUNCHER`, sin `.nds`, es que Windows esconde la extensión: escribe solo `_picoboot`. Si escribes
   `_picoboot.nds`, se quedará como `_picoboot.nds.nds` y el cartucho no lo encontrará.
6. De `Pico_Loader_DSPICO`, copia sus cinco archivos dentro de la carpeta `_pico` de la microSD.

La microSD tiene que quedar así, además de las carpetas que tú pongas. Lo que acaba en `/` es una carpeta,
y lo que va más a la derecha está dentro de la carpeta de encima:

```
_picoboot.nds
_pico/
    themes/
    aplist.bin
    patchlist.bin
    picoLoader7.bin
    picoLoader9.bin
    savelist.bin
```

La guía oficial del DSpico todavía lista cuatro archivos de Pico Loader. El quinto, `patchlist.bin`,
llegó con Pico Loader 1.5.0 y también hace falta.

> [!TIP]
> La [guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/) enlaza un
> paquete de flashcarts.net que trae todo esto en un solo zip, con `_picoboot.nds` ya renombrado: se
> descomprime y lo que trae dentro se copia en la raíz de la microSD. No es del LNH Team. Lo comprobamos
> el 28 de octubre de 2026: sus archivos eran idénticos a los oficiales de Pico Launcher 1.3.0 y Pico
> Loader 1.7.1. Antes de usarlo, mira en esa guía qué versiones trae: lo pone en inglés, debajo del
> enlace del paquete, en la línea que empieza por «Currently updated to».

## Los juegos

Copia tus juegos en la microSD. Pueden ir en cualquier carpeta; la guía oficial recomienda meterlos en
una, por ejemplo `Juegos`.

Los juegos de DS son archivos `.nds`; el menú también muestra los `.srl` y los `.dsi`. Si un juego está
dentro de un archivo comprimido, como un `.zip` o un `.7z`, descomprímelo antes: el menú no muestra los
comprimidos. Los de GBA (`.gba`) no salen sin una configuración aparte, que no está en esta página.

La partida se guarda junto al juego, en un archivo con el mismo nombre y la extensión `.sav`. Si mueves o
renombras un juego, haz lo mismo con su `.sav`: si no, el juego empieza sin tu partida.

## El primer arranque

1. Expulsa la microSD antes de sacarla de la computadora: en Windows, haz clic derecho en la unidad y
   elige «Expulsar»; en Mac, pulsa el botón de expulsar que sale junto a la tarjeta en el Finder. Si la
   sacas sin expulsarla, algún archivo puede quedar a medias.
2. Con la consola apagada, mete la microSD en el cartucho y el cartucho en la consola.
3. Enciende la consola. En una DS o una DS Lite, el cartucho sale en el menú de la consola como «DSpico»,
   de «LNH team»: ábrelo. En una DSi o una 3DS puede salir así, con el icono de una frambuesa, o como
   «Nintendo DS Demonstration», con un icono gris; las dos cosas son normales. En una DSi puede abrirse
   solo, sin pasar por el menú. Si no sale, o al abrirlo da un error, mira [Si no arranca](#si-no-arranca).
4. Se abre Pico Launcher y muestra lo que hay en la microSD. Busca tu juego y ábrelo con A.

En Pico Launcher, la cruceta mueve el cursor, A abre una carpeta o un juego, B vuelve a la carpeta
anterior, y L y R pasan rápido la lista cuando una carpeta tiene muchos archivos. También se puede usar la
pantalla táctil. Los ajustes están en el icono del engranaje. El menú solo está en inglés.

Para salir de un juego y volver al menú, guarda la partida y apaga la consola: Pico Loader todavía no
permite volver al menú desde un juego. Al encender otra vez, Pico Launcher tendrá seleccionado el último
juego que abriste.

Verás también la carpeta `_pico` y el archivo `_picoboot.nds`. No los borres ni les cambies el nombre:
sin ellos el cartucho no arranca. Si no quieres verlos, puedes
[ocultarlos](#ocultar-carpetas-y-archivos-del-menú).

### Si no arranca

Los errores salen como un texto en inglés. En una DSi o una 3DS con el firmware WRFUxxed, algunos salen en
cambio como una pantalla de un solo color.

- Si la consola no ve el cartucho, o se queda colgada al encenderla con él puesto, comprueba que la
  microSD está dentro y en FAT32. Si lo está pero no la formateaste con los pasos de
  [La microSD](#la-microsd), formatéala con ellos y prueba otra vez. Si sigue igual, mira
  [¿Necesito flashearlo?](firmware.md#necesito-flashearlo).
- En una DSi o una 3DS, si el cartucho sale en el menú de la consola pero al abrirlo aparece «Se ha
  producido un error» y te pide apagarla, mira
  [Si tu DSi o tu 3DS dice «Se ha producido un error»](firmware.md#si-tu-dsi-o-tu-3ds-dice-se-ha-producido-un-error).
- «Error: Failed to mount SD card.» o una pantalla azul: el cartucho no puede leer la microSD. Comprueba
  que está en FAT32 y, si lo está, prueba con otra, de marca y original. En una DSi con Unlaunch, si lo
  abriste desde TWiLight Menu++ o con la opción de cartucho de Unlaunch, prueba a abrirlo desde el menú
  normal de la DSi: lo explica [Qué cuenta como modificada](firmware.md#qué-cuenta-como-modificada).
- «ERROR: Failed to open Pico Loader file.» o una pantalla roja: faltan `picoLoader9.bin` o
  `picoLoader7.bin` dentro de `_pico`. Vuelve a copiar los archivos de Pico Loader.
- «ERROR: Failed to read Pico Loader file.»: los archivos de Pico Loader están, pero no se pueden leer.
  Vuelve a copiarlos y, si sigue igual, prueba con otra microSD, de marca y original.
- «Failed to open the rom file.», seguido de `fat:/_picoboot.nds`: falta `_picoboot.nds` en la raíz o
  tiene otro nombre, como `LAUNCHER.nds` o `_picoboot.nds.nds`. En Windows, este último puede verse como
  `_picoboot.nds`: lo explica el paso 5 de
  [Instalar Pico Launcher y Pico Loader](#instalar-pico-launcher-y-pico-loader).

## Ocultar carpetas y archivos del menú

Pico Launcher no muestra los archivos y carpetas ocultos, ni los que tienen un nombre que empieza por
punto. Por eso no salen los archivos que empiezan por `._`, que el Mac crea en la tarjeta al copiar.

Para que no salgan `_pico` ni `_picoboot.nds`, ponles el atributo de oculto. El cartucho los sigue
encontrando, porque los busca por su nombre.

- En Windows, haz clic derecho en la carpeta o el archivo, elige «Propiedades», marca «Oculto» y pulsa
  «Aceptar». Con la carpeta `_pico`, Windows pregunta además si aplicar el cambio a lo que tiene dentro:
  elige la opción que incluye las subcarpetas y los archivos, como hace la guía de Sanrax, y pulsa
  «Aceptar».
- En Mac, abre Terminal (está en Aplicaciones, dentro de Utilidades), escribe `chflags hidden` y un
  espacio, arrastra a la ventana la carpeta o el archivo y pulsa Retorno. Para deshacerlo, primero haz que
  se vean en el Finder, como explica el párrafo de abajo, y repite lo mismo con `chflags nohidden`.
- En Linux, o si no quieres tocar atributos, una carpeta tuya se oculta poniéndole un punto delante del
  nombre, por ejemplo `.Juegos-viejos`. No lo hagas con `_pico` ni con `_picoboot.nds`: el cartucho
  dejaría de encontrarlos.

Después tampoco los verás en la computadora, salvo que actives la opción de ver los elementos ocultos. En
el Explorador de archivos de Windows, marca «Elementos ocultos», que está en el menú «Ver» (en Windows 10,
en la pestaña «Vista»). En el Finder del Mac se activa y se desactiva con Comando + Mayúsculas + punto.

## Actualizar

Para tener una versión nueva de Pico Launcher o de Pico Loader no hace falta tocar el firmware: basta con
cambiar sus archivos de la microSD. Actualiza los dos a la vez: algunas funciones nuevas de Pico Loader,
como los trucos, solo funcionan con un Pico Launcher que también las tenga.

Si ocultaste `_pico` o `_picoboot.nds`, antes de empezar activa la opción de ver los elementos ocultos
(lo explica el final de [Ocultar carpetas y archivos del menú](#ocultar-carpetas-y-archivos-del-menú)). Al
terminar, vuelve a ocultar el `_picoboot.nds` nuevo, porque no viene oculto.

1. Descarga los dos zips nuevos y descomprímelos, como en
   [Instalar Pico Launcher y Pico Loader](#instalar-pico-launcher-y-pico-loader).
2. De `Pico_Launcher`, abre la carpeta `_pico/themes` y copia las carpetas que hay dentro (`material` y
   `raspberry`) en la carpeta `_pico/themes` de la microSD. Si la computadora pregunta, acepta
   reemplazarlas. No copies la carpeta `_pico` entera encima de la tuya: en Mac, el Finder la reemplaza y
   borra todo lo que tenía dentro, también tus ajustes, que están en `_pico/settings.json`. Ese archivo no
   viene en ninguna descarga: lo crea Pico Launcher la primera vez que arranca.
3. Copia el `LAUNCHER.nds` nuevo en la raíz, borra el `_picoboot.nds` viejo y cambia el nombre del nuevo
   a `_picoboot.nds`, igual que al instalar. Si se queda como `LAUNCHER.nds`, el cartucho no arranca.
4. De `Pico_Loader_DSPICO`, copia los archivos dentro de `_pico` y acepta reemplazar los que ya están.
   Cópialos todos: una versión nueva puede traer alguno más, como pasó con `patchlist.bin`.

## Fuentes

Esta página se basa en la [guía oficial del DSpico](https://github.com/LNH-team/dspico/blob/develop/GUIDE.md),
en el código y la documentación de [Pico Launcher](https://github.com/LNH-team/pico-launcher) y de
[Pico Loader](https://github.com/LNH-team/pico-loader), y en el código del
[firmware](https://github.com/LNH-team/dspico-firmware), el
[bootloader](https://github.com/LNH-team/dspico-bootloader) y
[WRFUxxed](https://github.com/LNH-team/dspico-wrfuxxed) del DSpico y de
[sdFormatWindows](https://github.com/flashcarts/sdFormatWindows). También usa la
[guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/) y su
[tutorial de formateo](https://sanrax.github.io/flashcart-guides/tutorials/formatting/), la
[página de preparación de la tarjeta de dsi.cfw.guide](https://dsi.cfw.guide/sd-card-setup.html), la
[guía rápida de DS de flashcarts.net](https://www.flashcarts.net/ds-quick-start-guide) y casos de usuarios
en r/flashcarts. Casi todas están en inglés.
