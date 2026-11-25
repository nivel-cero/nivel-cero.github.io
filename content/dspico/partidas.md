---
title: "Partidas"
BookIcon: disquete
weight: 38
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1"]
reviewed: 2026-11-24
---

En el DSpico, la partida de cada juego es un archivo de la microSD. Esta página explica dónde está, cómo
hacer copias, cómo traer las partidas que ya tienes de otro cartucho, de un emulador o de tu cartucho
original, y qué hacer si un juego no guarda. Todo es para Pico Launcher 1.3.0 y Pico Loader 1.7.1, las
últimas versiones en noviembre de 2026.

## Dónde está tu partida

La partida de un juego de DS es un archivo con el mismo nombre que el juego y la extensión `.sav`, en la
misma carpeta. La de `Juegos/Pokemon Platino.nds` es `Juegos/Pokemon Platino.sav`.

No tienes que crearla tú: Pico Loader, el programa del DSpico que arranca los juegos, la crea la primera
vez que abres el juego. Algunos juegos no guardan nada, y esos no tienen `.sav`. Pico Launcher no muestra
los `.sav` en la lista de juegos: solo se ven en la computadora.

Como la partida está en la microSD, es la misma en cualquier consola: puedes jugar en una DS Lite y
seguir en una 3DS.

En la computadora, el juego y su partida se llaman igual y solo cambia la extensión. En Windows, antes de
tocar nada, haz que se vean las extensiones: en el Explorador de archivos, «Ver» > «Mostrar» >
«Extensiones de nombre de archivo» (en Windows 10, pestaña «Vista»). Si no, puedes borrar el juego
creyendo que es la partida, o dejar la partida con dos extensiones, como `Pokemon Platino.sav.sav`.

Si mueves un juego a otra carpeta o le cambias el nombre, haz lo mismo con su `.sav`. Si no, el juego
empieza sin tu partida; si te pasa, mira [Si no guarda](#si-no-guarda).

Cada vez que cambies una partida desde la computadora (copiarla a la microSD, borrarla o cambiarle el
nombre), termina igual. En Mac, borra los archivos `._` con el comando de
[Pantalla negra en una DSi o una 3DS, con un Mac](problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac).
Después, expulsa la microSD antes de sacarla de la computadora, como en
[El primer arranque](primeros-pasos.md#el-primer-arranque).

Los juegos de GBA también guardan en un `.sav` junto al juego, pero GBARunner3 no siempre lo escribe en la
microSD en el momento de guardar: lo explica [Juegos de GBA](gba.md#partidas). Los emuladores de otras
consolas guardan cada uno a su manera: [Otros emuladores](otros-emuladores.md) dice dónde guardan GameYob,
nesDS, S8DS y NitroGrafx.

## Cuándo se guarda

El DSpico guarda cuando guarda el juego: cuando eliges guardar dentro del juego o cuando el juego guarda
solo. En ese momento, Pico Loader escribe la partida en la microSD. No hay nada que se guarde al apagar:
si apagas sin guardar, pierdes lo que jugaste desde la última vez, igual que con el cartucho original.

Mientras el juego guarda, no apagues la consola, y después espera unos segundos antes de apagarla. No
saques nunca el cartucho con la consola encendida.

## Hacer copias

Ni Pico Launcher ni Pico Loader hacen copias de tus partidas. Si un `.sav` se daña o lo borras, solo lo
recuperas si hiciste una copia. Haz una de vez en cuando, y siempre antes de formatear la microSD.

1. Apaga la consola, saca la microSD del cartucho y métela en la computadora.
2. Copia los `.sav` a una carpeta nueva de la computadora, con la fecha en el nombre, por ejemplo
   `Partidas 2026-11-24`. Así no reemplazas la copia anterior y sabes de cuándo es cada una. Si tienes
   DSiWare, copia también sus `.prv` y `.pub`. Lo más fácil es copiar entera la carpeta de los juegos.
3. Expulsa la microSD antes de sacarla de la computadora.

La fecha que muestra la computadora no sirve para saber cuándo guardaste. Las partidas que crea Pico
Loader salen con fecha del 1 de enero de 2018, y la fecha no cambia cuando el juego guarda. Si tienes
varias copias y no sabes cuál es la buena, guarda aparte en la computadora la partida que tienes ahora y
prueba las copias en el juego de una en una.

Para volver a una copia, ponla en la carpeta del juego con el nombre del juego y `.sav`, y reemplaza la
que haya. Lo que hayas jugado desde que hiciste esa copia se pierde. Si vuelves a poner varias, por
ejemplo después de formatear, cópialas en una sola tanda y sin copiar nada más al mismo tiempo: un `.sav`
partido en muchos trozos da [«Failed to setup save file.»](problemas.md#failed-to-setup-save-file), en
«Problemas».

## Empezar de cero

Para empezar un juego desde el principio, borra su `.sav` en la computadora, o muévelo a otra carpeta si
quieres conservarlo. La próxima vez que abras el juego, Pico Loader crea una partida nueva, vacía.

También puedes borrarla desde el propio juego, si tiene esa opción. Con The Legend of Zelda: Phantom
Hourglass, el juego se queda colgado al borrar la partida, en el mensaje que pide no apagar la consola, y
el 24 de noviembre de 2026 seguía sin arreglar. La partida sí se borra: si te pasa, apaga la consola.

## Traer tus partidas de otro cartucho o de TWiLight Menu++

Si jugabas con otro cartucho, como una R4, o con TWiLight Menu++ en una DSi o una 3DS, tus partidas
también son archivos `.sav` y se pueden pasar al DSpico. Lo que cambia es dónde las deja cada menú, el
programa que muestra la lista de juegos (en el DSpico, Pico Launcher):

| Menú | Dónde deja la partida |
|---|---|
| Wood R4, en la R4 original y la R4i Gold 3DS | Junto al juego, como `Juego.sav` |
| YSMenu, en el DSTT y las R4 parecidas | Junto al juego, como `Juego.sav` |
| AKMenu-Next | Junto al juego, como `Juego.sav`, salvo que lo cambies en sus ajustes |
| AKAIO, en la Acekard 2i | Como `Juego.sav` |
| TWiLight Menu++, en una DSi, una 3DS o un cartucho | En una carpeta `saves` dentro de la carpeta del juego, salvo que lo cambies en sus ajustes |
| Pico Launcher, en otro cartucho | Junto al juego, como `Juego.sav`, igual que en el DSpico |

Si el menú guardaba varias partidas de un mismo juego, cada una es un archivo distinto, como
`Juego.1.sav` o `Juego.sav1`: elige la que quieras seguir jugando. Si en la tarjeta del otro cartucho
falta la partida de algún juego, puede estar oculta: activa la opción de ver los elementos ocultos, como
explica el final de
[Ocultar carpetas y archivos del menú](primeros-pasos.md#ocultar-carpetas-y-archivos-del-menú). Una
partida oculta funciona igual en el DSpico.

Si vas a usar en el DSpico la misma microSD del otro cartucho, no hace falta copiar nada: basta con que
cada partida esté junto a su juego, con su mismo nombre y `.sav`. Si no, sigue estos pasos:

1. Mete en la computadora la microSD del otro cartucho, o la SD de la DSi o la 3DS, y copia la partida a
   la computadora. Después, expulsa esa tarjeta y mete la microSD del DSpico.
2. Copia la partida a la microSD del DSpico, en la misma carpeta que el juego.
3. Cámbiale el nombre para que se llame igual que el juego, con `.sav` al final: en Windows, selecciónala
   y pulsa F2; en Mac, selecciónala y pulsa Retorno. Si en el DSpico el juego es `Pokemon Platino.nds`, la
   partida tiene que ser `Pokemon Platino.sav`, aunque en el otro cartucho se llamara distinto, como
   `Pokemon Platino.nds.sav`. Si ya hay otro `.sav` con ese nombre, porque abriste el juego antes en el
   DSpico, bórralo primero; lo que jugaras con él se pierde.
4. En Mac, borra los archivos `._` con el comando de
   [Pantalla negra en una DSi o una 3DS, con un Mac](problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac).
   Después, expulsa la microSD antes de sacarla de la computadora, como en
   [El primer arranque](primeros-pasos.md#el-primer-arranque).
5. Mete la microSD en el cartucho, enciende la consola y abre el juego. Tiene que salir tu partida.

No hace falta cambiar el tamaño de la partida. Si es más pequeña de lo que necesita el juego, Pico Loader
la agranda sin tocar lo que tiene (salvo con Daigassou! Band-Brothers DX, que solo salió en Japón), y si
es más grande, la deja como está.

Si el juego empieza de cero, mira primero [Si no guarda](#si-no-guarda). Si el nombre y la carpeta están
bien, puede que tu cartucho guardara las partidas en otro formato: pregunta en
[r/NivelCero](https://www.reddit.com/r/NivelCero/), la comunidad de esta guía en Reddit, y di qué cartucho
y qué menú usabas. Con partidas de AKAIO, a un usuario le salía
[«Failed to setup save file.»](problemas.md#failed-to-setup-save-file), en «Problemas».

Para llevar una partida del DSpico a TWiLight Menu++, haz lo contrario: ponla en la carpeta `saves` que
está dentro de la carpeta del juego, con el nombre que tenga allí el juego y `.sav`, y reemplaza la que
haya. Si esa carpeta no está, créala con ese nombre, `saves`.

## Pasar tu partida a un emulador o traerla de uno

melonDS guarda igual que el DSpico: `Juego.sav`, junto al juego, salvo que en sus ajustes le hayas puesto
otra carpeta para las partidas. Puedes copiar la partida de uno a otro sin convertirla, pero tiene que
llamarse como el juego en cada sitio: cámbiale el nombre como en el paso 3 de
[Traer tus partidas de otro cartucho o de TWiLight Menu++](#traer-tus-partidas-de-otro-cartucho-o-de-twilight-menu).

DeSmuME guarda en otro formato, `.dsv`, en su propia carpeta (en Windows, de fábrica, la carpeta `Battery`
que está junto al programa). Para pasar al DSpico una partida de DeSmuME en Windows:

1. Abre el juego en DeSmuME.
2. Elige «File» > «Export Backup Memory...». Deja el tipo que sale, «Raw Save format (*.sav)», y guarda la
   partida con un nombre que acabe en `.sav`. Con el otro tipo, «No$GBA Save format», la partida no sirve
   para el DSpico.
3. Mete la microSD del DSpico en la computadora y sigue desde el paso 2 de
   [Traer tus partidas de otro cartucho o de TWiLight Menu++](#traer-tus-partidas-de-otro-cartucho-o-de-twilight-menu).

Para llevar una partida del DSpico a DeSmuME en Windows, abre el juego, elige «File» > «Import Backup
Memory...» y elige el `.sav`. Sale una ventana, «Import backup memory», que pregunta el tamaño de la
partida: deja lo que viene marcado y pulsa «OK». DeSmuME reinicia el juego con esa partida.

DeSmuME para Mac tiene otros menús, y esta guía no los explica: si lo usas, pregunta en
[r/NivelCero](https://www.reddit.com/r/NivelCero/).

## La partida de tu cartucho original

Para pasar al DSpico la partida de un cartucho original de DS, hace falta copiarla con un programa en
una consola modificada. Si la tuya no lo está, no te recomendamos modificarla solo para esto.

- En una 3DS con [CFW](../glosario.md#cfw), usa
  [Checkpoint](https://github.com/BernardoGiordano/Checkpoint). Mete el cartucho original antes de abrir
  Checkpoint, porque de fábrica no ve los que metes después: sale el primero de la lista. Elígelo, pulsa
  «Backup» («Copia» si Checkpoint está en español) y acepta el nombre que te propone, que es la fecha y la
  hora. La partida queda en la SD de la 3DS, en `3ds/Checkpoint/saves`: dentro hay una carpeta con el
  código del juego y su nombre en mayúsculas, y dentro de esa, otra con la fecha de la copia.
- En una DSi con [Unlaunch](../glosario.md#unlaunch), usa
  [GodMode9i](https://github.com/DS-Homebrew/GodMode9i), abierto desde la SD de la DSi. Con el cartucho
  original metido, elige «NDS GAMECARD» y, en las opciones, la de copiar solo la partida, «Save». Si
  GodMode9i está en español, son «TARJETA DE JUEGO NDS» y «Archivo de guardado». La partida queda en la SD
  de la DSi, en la carpeta `gm9i/out`, con el nombre del juego en mayúsculas, su código y su versión.

Después, sigue los pasos numerados de
[Traer tus partidas de otro cartucho o de TWiLight Menu++](#traer-tus-partidas-de-otro-cartucho-o-de-twilight-menu).

## DSiWare

Los DSiWare, los juegos y programas de la tienda de la DSi, no guardan en un `.sav`. Pico Loader crea
junto al juego dos archivos con su mismo nombre, `Juego.prv` y `Juego.pub`, o solo uno de los dos, según
lo que use cada DSiWare. Algunos no usan ninguno.

Si traes la partida de un DSiWare desde TWiLight Menu++, busca esos archivos, con los mismos nombres, en
la carpeta `saves` que está dentro de la carpeta del juego, y ponlos junto al juego en la microSD del
DSpico. Si acaban en un número, como `Juego.pr1` y `Juego.pu1`, cámbiales el nombre a `Juego.prv` y
`Juego.pub`. Si en lugar de esos archivos hay un `Juego.sav`, esa partida no sirve para el DSpico.

Guarda antes una copia en la computadora: si uno de los dos archivos es más pequeño de lo que pide el
juego, Pico Loader lo vacía al abrir el juego, y pierdes lo que tenía. No está comprobado que una partida
traída así funcione.

## Si no guarda

Si al abrir un juego empieza de cero, o si guardas y la siguiente vez no está tu partida, revisa estos
apartados en orden. Si es un juego de GBA, mira antes [Partidas](gba.md#partidas), en «Juegos de GBA»: en
una DSi o una 3DS hay que salir con POWER. Si es de otra consola, mira su apartado en
[Otros emuladores](otros-emuladores.md): nesDS, por ejemplo, solo guarda si se lo pides en su menú.

Si al abrir el juego sale «Failed to setup save file.», es otra cosa: mira
[ese mensaje](problemas.md#failed-to-setup-save-file) en «Problemas».

### El nombre no coincide

La partida tiene que llamarse igual que el juego, letra por letra, con `.sav` en lugar de `.nds`.

- Si se llama `Juego.nds.sav`, quítale el `.nds`.
- Windows esconde de fábrica las extensiones: si la partida se ve como `Juego.nds`, en realidad es
  `Juego.nds.sav`, y si se ve como `Juego.sav`, puede ser `Juego.sav.sav`. Para ver los nombres
  completos, en el Explorador de archivos elige «Ver» > «Mostrar» > «Extensiones de nombre de archivo»
  (en Windows 10, pestaña «Vista»).
- En Mac, el Finder también puede esconderlas. Selecciona el archivo, elige «Archivo» > «Obtener
  información» y mira el nombre completo en «Nombre y extensión». Si está mal, corrígelo ahí mismo.
- Si moviste el juego a otra carpeta o le cambiaste el nombre, su `.sav` se quedó en la carpeta de antes o
  con el nombre de antes.

### Se creó una partida nueva y vacía

Si el nombre no coincidía, al abrir el juego Pico Loader creó una partida nueva y vacía con el nombre
correcto, y la tuya se quedó como estaba. Para recuperarla:

1. Copia las dos a la computadora, cada una en una carpeta distinta, por si acaso. Si la tuya estaba en
   otra carpeta, las dos se llaman igual, y al copiarlas juntas una reemplazaría a la otra.
2. En la microSD, borra la nueva: la que está en la carpeta del juego y con su mismo nombre. Si jugaste
   algo con ella, lo pierdes.
3. Ponle a la tuya ese nombre y déjala en la carpeta del juego.

### Tienes el juego dos veces

Si tienes el mismo juego en dos carpetas o con dos nombres, cada uno tiene su propia partida, y puede que
estés abriendo el otro.

### Falta `savelist.bin`

Pico Loader mira en `_pico/savelist.bin` cuánto ocupa la partida de cada juego. Si falta, no avisa: les da
a todos 512 KB, y los pocos juegos que necesitan más, como The Legend of Zelda: Spirit Tracks, pierden
parte de lo que guardan. Comprueba que está en la carpeta `_pico` de la microSD. Si no, vuelve a copiar
los archivos de Pico Loader como en el paso 4 de [Actualizar](primeros-pasos.md#actualizar).

### La microSD

Una microSD falsa o de mala calidad puede fallar al escribir: el juego tarda mucho en guardar, no guarda
o la partida sale dañada. A dos usuarios con estos fallos se les arregló al cambiar por una de marca la
microSD que venía con el cartucho. Para probar la tuya, guarda poco después de empezar un juego, apaga la
consola, enciéndela y mira si carga la partida. Para elegir otra, mira
[Qué necesitas](primeros-pasos.md#qué-necesitas).

### La partida está dañada

Si el juego dice que la partida está dañada, no se puede arreglar: vuelve a tu última copia. Si la acabas
de traer de otro cartucho o de un emulador, la de allí sigue bien, y puede que esté en otro formato, como
explica
[Traer tus partidas de otro cartucho o de TWiLight Menu++](#traer-tus-partidas-de-otro-cartucho-o-de-twilight-menu).
Revisa también la microSD, como explica el apartado de arriba.

Si sigue sin guardar, pregunta como explica
[Si nada de esto funciona](problemas.md#si-nada-de-esto-funciona).

## Lo que el DSpico no hace

El DSpico no tiene estados de guardado, que dejan guardar en cualquier momento y volver a ese punto.

Las partidas van siempre junto al juego: Pico Launcher 1.3.0 no tiene ningún ajuste para guardarlas en
una carpeta aparte.

Tampoco tiene varias partidas para un mismo juego. Si quieres dos, copia el juego con otro nombre, por
ejemplo `Pokemon Platino 2.nds`: tendrá su propia partida, `Pokemon Platino 2.sav`.

## Fuentes

Esta página se basa en el código y las issues de [Pico Loader](https://github.com/LNH-team/pico-loader)
1.7.1, en el código de [Pico Launcher](https://github.com/LNH-team/pico-launcher) 1.3.0 y del
[firmware del DSpico](https://github.com/LNH-team/dspico-firmware) 1.0.1, y en el de
[TWiLight Menu++](https://github.com/DS-Homebrew/TWiLightMenu),
[AKMenu-Next](https://github.com/coderkei/akmenu-next),
[Checkpoint](https://github.com/BernardoGiordano/Checkpoint),
[GodMode9i](https://github.com/DS-Homebrew/GodMode9i), [DeSmuME](https://github.com/TASEmulators/desmume) y
[melonDS](https://github.com/melonDS-emu/melonDS). Lo de Wood R4, YSMenu y AKAIO sale de sus ajustes y sus
notas, en los paquetes que enlaza la
[guía de flashcarts de Sanrax](https://sanrax.github.io/flashcart-guides/). También usa casos de usuarios
en r/DsPico y r/flashcarts. Casi todas están en inglés.
