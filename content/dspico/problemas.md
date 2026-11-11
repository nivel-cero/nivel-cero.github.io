---
title: "Problemas"
BookIcon: aviso
weight: 40
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1", "Firmware oficial 1.0.1"]
reviewed: 2026-11-05
---

Esta página va por lo que ves en la pantalla. Los mensajes del DSpico salen siempre en inglés, da igual el
idioma de la consola, y aquí están copiados tal cual: si te sale uno, búscalo en esta página con Ctrl+F
(Comando + F en Mac, o «Buscar en la página» en el navegador del celular). Los mensajes de error que
salen al encender, antes del menú, están en [Si no arranca](primeros-pasos.md#si-no-arranca), en «Primeros pasos».

## Antes que nada

En los casos que revisamos para esta página, la causa que más se repite es la microSD. Antes de buscar tu
problema más abajo, comprueba estas cuatro cosas:

1. Que la microSD es de marca y original. Si usas la que vino con el cartucho, cámbiala. Un usuario con la
   de 8 GB que traía su DSpico solo podía abrir un juego; al pasarlo todo a una de 32 GB comprada en una
   tienda, funcionaron todos. Otros veían pantallas blancas o «Failed to load arm9.» y lo arreglaron
   cambiando de microSD. Una tarjeta mala también puede hacer que un juego vaya lento: con una Amazon
   Basics, en Pokémon Platino cada combate contra un Pokémon salvaje tardaba 30 segundos o más en empezar.
2. Que está en FAT32. Lo explica [La microSD](primeros-pasos.md#la-microsd).
3. Que tienes la última versión de Pico Launcher y de Pico Loader. Las versiones nuevas de Pico Loader
   traen arreglos para juegos concretos. Pico Launcher no muestra su versión en ninguna parte, así que si
   no sabes cuál tienes, vuelve a copiar los dos con los pasos de [Actualizar](primeros-pasos.md#actualizar).
   Copia todos los archivos de Pico Loader: si falta `aplist.bin` o `patchlist.bin`, no avisa, y algunos
   juegos se quedan en blanco.
4. Que el firmware del cartucho no es el 1.0.0. El 1.0.1, de febrero de 2026, arregla un fallo al escribir
   en la microSD que daba problemas con varias tarjetas. El firmware tampoco muestra su versión: si ya
   probaste con una microSD buena y los juegos se siguen colgando, mira
   [¿Necesito flashearlo?](firmware.md#necesito-flashearlo).

## La consola no ve el cartucho

Al encender, el firmware del cartucho intenta leer la microSD. Si no puede, se pone en modo de flasheo
(espera a que le grabes un firmware por USB) y la consola no lo ve: no sale en el menú, o una DS Lite se
queda en la advertencia de salud y seguridad. Sin microSD pasa lo mismo, y es normal.

- Comprueba que la microSD está bien metida y en FAT32, como dice
  [Si no arranca](primeros-pasos.md#si-no-arranca).
- Si está en FAT32 y sigue igual, copia todo a la computadora, formatéala con los pasos de
  [La microSD](primeros-pasos.md#la-microsd) aunque ya lo esté, y vuelve a copiarlo. Un usuario tenía una
  tarjeta con el esquema de particiones GPT, que el cartucho no lee; al formatearla con el esquema MBR, el
  que dejan esos pasos, funcionó.
- Prueba el cartucho en otra consola. Si allí funciona, mira la ranura de la tuya. Un usuario con una DSi
  vio que también le costaba leer algunos juegos originales, y en las DSi de dos amigos el DSpico
  funcionó. A otro, con una DS Lite que decía que no había tarjeta, le aconsejaron limpiar los contactos
  de la ranura con alcohol isopropílico. Si el cartucho entra muy justo, mira si la carcasa tiene
  rebabas de plástico: un usuario las limó y dejó de fallar.
- Si es nuevo y no sale en ninguna consola, puede que te llegara sin firmware. A un usuario con un DSpico
  recién comprado, que no salía ni en su DSi ni en su DS Lite, le funcionó al flashearlo: mira
  [¿Necesito flashearlo?](firmware.md#necesito-flashearlo).

## Se queda colgado al encender

Si la consola ve el cartucho pero no llega al menú de Pico Launcher, busca abajo lo que ves en la pantalla.

### Pantalla negra en una DSi o una 3DS, con un Mac

Cuando el Mac copia un archivo a una microSD en FAT32, crea al lado otro oculto con el mismo nombre y
`._` delante, como `._picoLoader7.bin` junto a `picoLoader7.bin`. Ahí guarda datos que solo usa el Mac.
En el Mac no se ven, pero el cartucho sí los encuentra.

Lo comprobamos el 10 de octubre de 2026. Con `._picoLoader7.bin` y `._picoLoader9.bin` dentro de `_pico`,
una New 3DS se quedaba en negro al abrir el DSpico, y una DS Lite arrancaba bien con la misma tarjeta. Al
borrar los archivos `._`, la New 3DS volvió a arrancar. Solo lo hemos visto en la New 3DS, pero una DSi o
cualquier otra 3DS arranca el cartucho igual que ella, así que también les puede pasar.

Copiar con cuidado no lo evita: el Mac vuelve a crear esos archivos cada vez que copias algo a la tarjeta.
Bórralos siempre antes de expulsarla:

1. Abre la Terminal, que está en «Aplicaciones» > «Utilidades».
2. Escribe esto, cambia `NOMBRE` por el nombre de la microSD tal como sale en el Finder y pulsa Retorno:

   ```
   find "/Volumes/NOMBRE" -name '._*' -delete
   ```

3. Expulsa la tarjeta desde el Finder.

El comando solo borra los archivos que empiezan por `._`. No toca tus juegos ni tus partidas.

### Dos pantallas blancas en una DS original

FlashMe es una modificación del sistema de la propia consola; si tu DS no muestra la advertencia de salud
y seguridad al encender, puede que lo tenga. Un usuario con FlashMe veía que el DSpico a veces se quedaba
en dos pantallas blancas, y encendiendo con SELECT pulsado le arrancaba siempre: prueba eso primero. Se
le arregló del todo al cambiar a FlashMe 0.8 (la «noauto»), pero eso es volver a flashear la consola.

### Se queda en la imagen del DSpico

Si pusiste un tema con música de fondo, prueba sin ella: a un usuario le pasaba eso y al quitar la música
se arregló. Para quitarla, cambia el nombre de la carpeta `bgm` que está dentro de la carpeta del tema,
en `_pico/themes`. Otro usuario aconseja que la música no dure más de 2 minutos y medio.

### Pantallas de colores y archivos dañados

A un usuario con una DSi le pasó dos veces: la pantalla de arriba salía azul y la de abajo negra con el
firmware WRFUxxed, o blanca arriba y roja abajo con Hybrid. En `_pico` faltaban muchos archivos y los
demás estaban dañados. Si te pasa, vuelve a copiar Pico Launcher y Pico Loader como en
[Actualizar](primeros-pasos.md#actualizar). Si se repite, copia todo a la computadora, formatea la
microSD y vuelve a copiarlo; si sigue, cambia de microSD.

### Se queda en WRFU Tester

Con el firmware WRFUxxed, en una DSi o una 3DS sale un momento `*** WRFU Tester v0.60 ***` en la pantalla
de abajo antes del menú. Si se queda ahí:

- En una DSi con HiyaCFW y una tarjeta SD grande en su propia ranura, la guía de Sanrax dice que WRFU
  Tester tarda mucho. Propone poner en la DSi una SD más pequeña o flashear el cartucho con Hybrid.
- Si no es tu caso, la guía oficial dice que el firmware se preparó mal. Hay que volver a flashearlo:
  mira [Cómo se flashea](firmware.md#cómo-se-flashea).

## Mensajes al abrir un juego

Si al abrir un juego sale un texto en inglés, con letras blancas sobre fondo negro, es un mensaje de Pico
Loader, el programa que arranca los juegos. La consola se queda parada y no se puede volver al menú:
apágala, y si no se apaga, mantén pulsado POWER unos segundos. Pico Loader 1.7.1 tiene
11 mensajes de error y un aviso, y aquí están todos.

### «Failed to open the rom file.»

Debajo sale la ruta del archivo que Pico Loader intentó abrir, y ese archivo no está ahí.

- Si la ruta es `fat:/_picoboot.nds`, mira [Si no arranca](primeros-pasos.md#si-no-arranca).
- Si es la de un emulador, abriste un archivo que se abre con él, como un `.gba`, y el emulador no está
  en la ruta que dice `_pico/settings.json`, que es la que sale en la pantalla. Ponlo en esa ruta.
- Si es la de tu juego pero le falta la carpeta (sale `fat:/Juego.nds` en vez de
  `fat:/Juegos/Juego.nds`), a un usuario se le arregló copiando todo a la computadora, formateando la
  microSD y volviendo a copiarlo.
- Si no, comprueba en la computadora que en esa ruta hay un archivo con ese nombre exacto.

### «Failed to load rom header.»

Pico Loader abrió el juego, pero no pudo leer su principio. O el archivo está vacío, o la lectura falló.
Mira en la computadora que el juego no pese 0 bytes y vuelve a copiarlo. Si te sale con todos los juegos,
prueba con otra microSD.

### «Failed to load arm9.» y «Failed to load arm7.»

Pico Loader no pudo leer entera una de las partes del juego. Puede salir en cualquier consola, y casi
siempre es la copia del juego o la microSD:

1. Borra el juego de la microSD y vuelve a copiarlo, sin copiar nada más al mismo tiempo. En r/flashcarts,
   al menos cuatro personas lo arreglaron así: habían copiado varios juegos al mismo tiempo, sacándolos
   directamente de los `.zip`. Una de ellas había vuelto a flashear el cartucho tres veces sin resultado.
   El porqué está en [Un juego partido en muchos trozos](#un-juego-partido-en-muchos-trozos).
2. Si sigue, prueba el mismo juego en otra microSD, de marca y original.

### «Failed to load arm9i.» y «Failed to load arm7i.»

Solo salen en una DSi o una 3DS, con juegos que tienen funciones de DSi: Pico Loader no pudo leer la
parte de DSi del juego. En una DS o una DS Lite no salen nunca, porque ahí esa parte no se usa.

Si a un juego comercial le falta esa parte, desde Pico Loader 1.7.0 sale en cambio el
[aviso de las partes de DSi](#warning-dsi-rom-detected-with-missing-dsi-parts). Estos dos errores
quedan para cuando la parte de DSi está, pero rota:

- En ROM hacks y traducciones que dejan rota esa parte. Dartz150, del LNH Team, aconseja pedir al autor
  que lo arregle. En noviembre de 2026 pasa con los hacks «Complete Unova Pokédex» de Pokémon Negro y
  Blanco y de Negro 2 y Blanco 2.
- En una copia mala del juego. Gericom, del LNH Team, pide comprobarla con la base de datos de No-Intro,
  que tiene los datos de las copias buenas de cada juego. Esta guía todavía no explica cómo hacerlo.
- En homebrew de DSi, porque a los homebrew Pico Loader no les hace la comprobación del aviso.

### «Failed to apply arm9 patches.» y «Failed to apply arm7 patches.»

Pico Loader cambia algunas partes de cada juego comercial para que funcione desde la microSD, y con este
juego no pudo.

1. Si es el error de arm7 y tienes trucos activados para ese juego, desactívalos: en Pico Launcher, pulsa
   Y sobre el juego y luego X, que los desactiva todos. Con trucos, Pico Loader hace un cambio más ahí.
2. Actualiza Pico Loader, como en [Actualizar](primeros-pasos.md#actualizar).
3. Comprueba la copia del juego con No-Intro. En los casos que respondió Gericom había una copia mala,
   versiones beta y un juego que lee el cartucho a su manera, Tropix!, arreglado en Pico Loader 1.4.0.
4. Si la copia es buena, es un juego que Pico Loader todavía no sabe arrancar. Avisa al LNH Team, como
   dice [Si nada de esto funciona](#si-nada-de-esto-funciona).

### «Failed to setup save file.»

Pico Loader no pudo preparar la partida, el archivo `.sav` que va junto al juego. Puede ser que la
microSD no tenga espacio para crearlo, que el `.sav` esté marcado como de solo lectura o que esté partido
en más de 13 trozos en la microSD, por ejemplo después de copiarlo desde la computadora.

1. Copia el `.sav` a la computadora, por si acaso.
2. Libera espacio en la microSD.
3. Quítale al `.sav` la marca de solo lectura. En Windows: clic derecho, «Propiedades», y desmarca
   «Solo lectura».
4. Si sigue, copia todo a la computadora, formatea la microSD y vuelve a copiarlo.

A un usuario que probó Pico Loader en una Acekard 2i le salía con las partidas que había creado AKAIO, el
menú de ese cartucho. Hay una issue (un aviso de fallo en GitHub) abierta y sin respuesta.

### «Failed to setup DSiWare save.»

Sale al abrir un DSiWare, si Pico Loader no puede preparar sus archivos. Puede pasar si el DSiWare está
metido en muchas carpetas, una dentro de otra: muévelo a una carpeta cerca de la raíz. Si el juego guarda
partida, comprueba también que hay espacio en la microSD.

### «Failed to setup Pico Loader info.»

Pico Loader no pudo leer bien sus propios archivos, `picoLoader9.bin` y `picoLoader7.bin`, que están en
`_pico`, por ejemplo porque están partidos en muchos trozos. También es el primer error que se ve si no
consigue leer la microSD. Vuelve a copiar los archivos de Pico Loader; si sigue, copia todo a la
computadora, formatea la microSD y vuelve a copiarlo.

### «WARNING: DSi ROM detected with missing DSi parts.»

Es un aviso: al pulsar A, Pico Loader sigue cargando el juego. Sale así:

```
WARNING: DSi ROM detected with missing DSi parts.
ROM will run in DS mode.

Press (A) to continue...
```

En una DSi o una 3DS, Pico Loader abre en modo DSi los juegos que tienen funciones de DSi. Si a tu copia
le falta la parte de DSi, avisa y, al pulsar A, abre el juego en modo DS. Pasa sobre todo con ROM hacks y
traducciones, y con copias malas. Otros cartuchos, como la R4, abren todo en modo DS, y por eso esas
copias funcionan en ellas sin aviso.

También puede salir con una copia buena, si el archivo está muy partido en la microSD: mira
[Un juego partido en muchos trozos](#un-juego-partido-en-muchos-trozos).

A dos usuarios con traducciones de Pokémon Blanco, uno con una 3DS, la pantalla se les quedaba en blanco
después del aviso. El 5 de noviembre de 2026 no lo arreglaba ninguna versión de Pico Loader.

## Pantalla blanca o negra, sin ningún mensaje

Al elegir un juego, Pico Launcher pone las dos pantallas en blanco, y siguen así hasta que el juego
dibuja su primera imagen. Si algo falla antes y Pico Loader no lo detecta, se quedan en blanco y no sale
ningún texto. Mira primero [Antes que nada](#antes-que-nada) y después estas causas.

### Un juego partido en muchos trozos

La microSD guarda cada archivo en trozos. Si haces varias copias al mismo tiempo, por ejemplo arrastrando
un juego mientras otro se sigue copiando o sacándolos directamente de un `.zip`, los trozos de cada juego
pueden quedar mezclados con los de los demás. Pico Loader 1.7.1 solo puede leer un juego partido en 61
trozos como mucho. Si está más partido, no avisa: lee datos equivocados, y el juego se queda en blanco o en
negro, o da otro error. Gericom, del LNH Team, dijo en septiembre de 2026 que Pico Loader debería avisar
con un mensaje; en la 1.7.1 todavía no lo hace.

- Borra el juego de la microSD y vuelve a copiarlo, sin copiar nada más al mismo tiempo.
- Si te pasa con muchos juegos, copia todo a la computadora, formatea la microSD y vuelve a copiarlo todo
  en una sola tanda: selecciónalo todo y arrástralo, y la computadora copiará los archivos uno detrás de
  otro. Los `.zip` descomprímelos antes en la computadora.

### Un juego cifrado sin el BIOS

Algunas copias de juegos de DS tienen cifrado su principio, la llamada zona segura. Pasa, por ejemplo,
con los juegos de DS sacados de la Consola Virtual de Wii U. Para abrirlas, Pico Loader necesita el BIOS
del procesador ARM7 de la DS, en un archivo llamado `biosnds7.rom` dentro de `_pico`. Si no está, no
avisa: el juego se queda con las dos pantallas en blanco. Un usuario con The World Ends With You, en dos
DS Lite y una DS, lo arregló poniendo ese archivo. Esta guía no lo enlaza. Si ya tienes `biosnds7.rom` y
el juego sigue en blanco, actualiza Pico Loader: a otro usuario le funcionó así.

Los DSiWare también necesitan `biosnds7.rom` y, además, archivos de la memoria interna de una DSi o una
3DS, que esta guía todavía no explica. Si los tienes y se quedan en blanco, prueba con otra microSD: a
dos usuarios con una DSi XL se les arregló así.

### Un truco activado

Los trucos que marcas en Pico Launcher se quedan activados para ese juego hasta que los desmarcas, y
algunos impiden que arranque. Pasa sobre todo con los que quitan la protección anticopia: Pico Loader ya
la quita por su cuenta con `aplist.bin`, y con el truco activado el juego se ha quedado en blanco a
varios usuarios. Para desactivarlos, pulsa Y sobre el juego y luego X.

## Juegos que no funcionan

El LNH Team no tiene una lista de juegos compatibles. Lo más parecido son las issues de Pico Loader con
la [etiqueta «game»](https://github.com/LNH-team/pico-loader/issues?q=is%3Aissue%20label%3Agame), donde la gente avisa
de los juegos que fallan. El 5 de noviembre de 2026 había 44, y 16 seguían abiertas. Están en inglés.

Si te falla alguno de estos, actualiza Pico Loader y comprueba que en `_pico` está `patchlist.bin`, porque
ya están arreglados:

- New Super Mario Bros. de EE. UU., GTA: Chinatown Wars, Kirby Mass Attack, Dementium II, Children of
  Mana, Luminous Arc 2, Prince of Persia: The Forgotten Sands y Castlevania: Portrait of Ruin, desde
  Pico Loader 1.5.0.
- Pokémon Ranger europeo, desde Pico Loader 1.7.0.

El 5 de noviembre de 2026 seguían sin arreglar:

- Pokémon Dash, que se queda en blanco. Gericom lo confirmó en agosto de 2026: el juego lee el cartucho
  a su manera y necesita un parche especial.
- Mario vs. Donkey Kong: Mini-Land Mayhem, que en una DS Lite no muestra los personajes. En una New 3DS
  XL sí salen.
- Varios ROM hacks de Pokémon HeartGold y SoulSilver, como Sacred Gold, Storm Silver, HeartGold
  Generations y Chrome Gold, que se quedan en blanco aunque los juegos originales funcionan. Pasa lo
  mismo con algunos hacks de Super Mario 64 DS, y con Pokémon Conquest con la traducción al español.
  Algunos usuarios los abren con otro programa que arranca juegos, nds-bootstrap, desde TWiLight Menu++
  o AKMenu-Next instalados en la misma microSD. Esta guía no explica cómo instalarlos.

Para la próxima versión de Pico Loader, el LNH Team ya tiene arreglados dos casos. GodMode9i se cuelga
al abrirlo en algunas versiones (a un usuario le funcionó la 3.8.0). Brain Age Express: Sudoku, un
DSiWare, dice «Download failed. Please try again.». Para la próxima versión de Pico Launcher tiene
arreglado el icono roto o con píxeles de colores de algunos ROM hacks.

## La DSi XL se apaga al cerrar la tapa

A algunos usuarios les pasa a veces dentro de un juego, por ejemplo en Hotel Dusk o en El profesor Layton y
el futuro perdido, y no hay una causa clara. A uno se le arregló al cambiar su SanDisk de 128 GB por una
Lexar de 64 GB. Otro vio que con la batería bien cargada no le pasaba, y que otra DSi XL con el mismo
cartucho y la misma microSD no lo tenía. La [issue de Pico Loader](https://github.com/LNH-team/pico-loader/issues/116) sigue abierta.

## La 3DS pide un PIN al abrir el DSpico

Es el control parental de la 3DS, no el cartucho: se cambia en la configuración de la consola.

## Un emulador se queda en blanco o colgado en una DSi

Algunos, como nesDS, necesitan que la DSi tenga una tarjeta SD en su propia ranura. Sirve cualquiera que
la DSi pueda leer, aunque esté vacía: a dos usuarios se les arregló así.

## Batería y luces

En una DS Lite, la luz de encendido se pone roja cuando queda poca batería. Hay quien la ve roja con el
DSpico y verde con juegos originales. Prueba primero a descargarla del todo y cargarla entera: a un
usuario, el icono de la pantalla le decía que estaba cargada, pero ese icono solo distingue entre normal
y baja, y la batería estaba baja de verdad. Si sigue pasando, puede ser una batería gastada o falsa.

El DSpico gasta poco. XLuma, del LNH Team, da un consumo medio de 57 mW, y un usuario midió en su DS
Lite 7 h 30 min de juego con el DSpico y 5 h 25 min con una R4, con el mismo brillo y sin sonido.

El menú de Pico Launcher todavía no tiene modo de reposo: si cierras la tapa en el menú, la consola sigue
encendida y, si tu tema tiene música, sigue sonando. Dentro de los juegos sí funciona.

La placa del DSpico tiene una luz roja y otra azul, pero el firmware oficial no las usa. Ninguna luz del
cartucho avisa de un error.

## Trucos

Los trucos se abren con Y sobre un juego. Si sale «No cheats found.», puede ser que falte
`_pico/usrcheat.dat`, que ese archivo no traiga el juego o que el juego sea un ROM hack o una traducción:
Pico Launcher busca los trucos por el principio del archivo del juego, y esos lo cambian. Los trucos
necesitan Pico Launcher 1.2.0 y Pico Loader 1.6.0 o posteriores; con un Pico Loader anterior no se
aplican, y no sale ningún aviso.

`usrcheat.dat` es la lista de trucos de DeadSkullzJr, y no viene con Pico Launcher. Si un truco no
funciona, avísale en su hilo de GBAtemp diciendo la consola, el cartucho, el menú (Pico Launcher), el
juego y qué truco falla.

## Partidas

- La partida es el archivo con el mismo nombre que el juego y la extensión `.sav`. Otros cartuchos la
  guardan como `Juego.nds.sav`: si vienes de uno de ellos, cambia el nombre a `Juego.sav`. En Windows,
  si las extensiones están ocultas, el archivo se ve como `Juego.nds`: escribe solo `Juego`.
- Si tienes el mismo juego dos veces, cada copia tiene su partida.
- Después de guardar, espera unos segundos antes de apagar, y no saques nunca el cartucho con la
  consola encendida. A un usuario que lo sacó justo después de guardar, el DSpico empezó a arrancar en
  una pantalla azul y perdió la partida.
- Haz copias de tus `.sav` en la computadora de vez en cuando.

## GBA

Los juegos de GBA tienen su propia página, [Juegos de GBA](gba.md). Ahí está el arreglo de Pokémon
Esmeralda en español y qué hacer si un juego se queda en blanco, en negro o en azul.

## Si nada de esto funciona

Pregunta en [r/flashcarts](https://www.reddit.com/r/flashcarts/) o en [r/DsPico](https://www.reddit.com/r/DsPico/).
Son foros de Reddit en inglés, pero también hay quien pregunta en español. Si crees que es un fallo de
Pico Loader con un juego, busca antes en sus issues con la
[etiqueta «game»](https://github.com/LNH-team/pico-loader/issues?q=is%3Aissue%20label%3Agame) y, si no
está, abre una nueva: hace falta una cuenta de GitHub, y se escribe en inglés. Da estos datos:

- La consola y su modelo, y si tiene algo instalado, como Unlaunch o HiyaCFW.
- La variante del firmware del cartucho, Hybrid o WRFUxxed. Lo explica
  [Qué variante lleva tu cartucho](firmware.md#qué-variante-lleva-tu-cartucho).
- Las versiones de Pico Launcher y Pico Loader que copiaste (si no lo sabes, actualízalos antes).
- La marca y el tamaño de la microSD.
- El juego, con su región, y si es un ROM hack o una traducción.
- El texto exacto de la pantalla, o una foto.
- Lo que ya probaste.

## Fuentes

Esta página se basa en el código y las issues de [Pico Loader](https://github.com/LNH-team/pico-loader)
y [Pico Launcher](https://github.com/LNH-team/pico-launcher), en el código del
[firmware](https://github.com/LNH-team/dspico-firmware), el
[bootloader](https://github.com/LNH-team/dspico-bootloader), [WRFUxxed](https://github.com/LNH-team/dspico-wrfuxxed)
y el [hardware](https://github.com/LNH-team/dspico-hardware) del DSpico, en la
[guía oficial](https://github.com/LNH-team/dspico/blob/develop/GUIDE.md) y en
[GBARunner3](https://github.com/Gericom/GBARunner3). También usa la
[guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/), casos de
usuarios en r/flashcarts, r/DsPico, r/nds y GBAtemp, y lo que probamos con una New 3DS y una DS Lite.
Casi todas están en inglés.
