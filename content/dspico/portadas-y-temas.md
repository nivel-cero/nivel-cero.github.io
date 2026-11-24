---
title: "Portadas y temas"
BookIcon: paleta
weight: 38
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1"]
reviewed: 2026-11-20
---

Pico Launcher puede mostrar una portada para cada juego, como la de su caja, y cambiar de aspecto con un
tema. Las dos cosas van en la microSD y las pones tú: Pico Launcher no trae portadas, y de temas solo
trae dos. Todo lo de esta página es para Pico Launcher 1.3.0, la última versión en noviembre de 2026.

## Qué se puede cambiar

Puedes poner portada a los juegos de DS, de GBA y de otras consolas. El tema cambia los colores, los
fondos de las dos pantallas, los recuadros de los juegos y, si la trae, la música de fondo.

Pico Launcher 1.3.0 no deja poner iconos propios a los juegos ni poner portada o icono a una carpeta. El
tema tampoco se elige desde la consola: se cambia en un archivo, desde la computadora. La próxima
versión, en la que trabaja el LNH Team, traerá las tres cosas, pero todavía no tiene fecha.

## Dónde salen las portadas

Pico Launcher tiene cuatro vistas. Para cambiar de vista:

1. En la pantalla de abajo está el icono del engranaje: arriba a la derecha en la cuadrícula horizontal
   (la de fábrica) y en Coverflow, y abajo a la izquierda en la cuadrícula vertical y en la lista. Ve a
   él con la cruceta y pulsa A, o tócalo. Se abre «Display Settings».
2. En la fila «Layout» hay cuatro botones sin texto, uno por vista. De izquierda a derecha: cuadrícula
   horizontal, cuadrícula vertical, lista y Coverflow.
3. Ve al botón de la vista que quieras con la cruceta y pulsa A, o tócalo. Después pulsa B para cerrar.
   Al encender otra vez, Pico Launcher sigue en esa vista.

En Coverflow, las portadas van en la pantalla de abajo, en un carrusel, y un juego sin portada sale con
un «?». El carrusel del tema de fábrica no es igual que el de los demás temas: si en un video ves otro
Coverflow, es por el tema. En las otras tres vistas, abajo van los iconos, y la portada del juego elegido
sale en la pantalla de arriba, junto a su nombre. Si no tiene portada, arriba solo salen el icono y el
nombre.

## Poner portadas con una herramienta

Las portadas van dentro de `_pico/covers`, en tres carpetas. Lo que va más a la derecha está dentro
de la carpeta de encima:

```carpetas
_pico/
    covers/
        nds/
            CPUS.bmp
        gba/
            BPES.bmp
        user/
            Super Mario Land.gb.bmp
```

- En `nds` y `gba`, cada portada se llama como el código del juego: cuatro letras o números que van
  dentro del archivo del juego, como `CPUS` para Pokémon Edición Platino en español. Pico Launcher no lo
  muestra, pero las herramientas lo leen solas.
- En `user`, cada portada se llama como el archivo del juego, con su extensión, más `.bmp`: la de
  `Super Mario Land.gb` es `Super Mario Land.gb.bmp`. Vale para cualquier juego. Si un juego tiene
  portada en `user` y también en `nds` o `gba`, sale la de `user`.

Estas carpetas no vienen con Pico Launcher. Las herramientas las crean al guardar la primera portada.

Hay tres herramientas que buscan las portadas de tus juegos y las guardan en la microSD con el formato
que pide Pico Launcher. Son gratis y funcionan en Chrome o en Edge, sin instalar nada más:

| Herramienta | Consolas | Idioma |
|---|---|---|
| [PicoCover](https://scaletta.github.io/PicoCover/) | DS y GBA | Inglés |
| [TwilightBoxart](https://twilightboxart.com/) | 26, entre ellas DS, GBA, Game Boy, NES, Super Nintendo y Mega Drive | Inglés |
| [PicoDex](https://rasalopa.github.io/picodex/) | 13, entre ellas DS, GBA, Game Boy, NES, Super Nintendo y Mega Drive | Varios, entre ellos español |

En Safari o en Firefox no pueden guardar en la microSD: PicoCover y TwilightBoxart te dan un `.zip`, y
PicoDex no abre la tarjeta. Ese `.zip` trae una carpeta `_pico`. No la copies encima de la de la microSD,
porque en Mac el Finder reemplaza la tuya y borra lo que tenía, como avisa
[Actualizar](primeros-pasos.md#actualizar).

PicoDex es de quien escribe esta guía. Sanrax enlaza las tres en su
[guía del DSpico](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/) (en inglés).

No guardan las portadas en el mismo sitio. PicoCover las guarda por código, en `nds` y `gba`.
TwilightBoxart las guarda todas por nombre, en `user`. PicoDex guarda las de DS y GBA por código y las de
otras consolas por nombre.

Los pasos son casi iguales en las tres:

1. Mete la microSD en la computadora. Tiene que tener ya Pico Launcher instalado, con su carpeta `_pico`.
2. Abre la herramienta en Chrome o en Edge.
3. Pulsa el botón para elegir la tarjeta. En PicoCover, deja marcada «Include GBA games», que ya viene
   marcada, y pulsa «Get Started» y «Browse for USB». En TwilightBoxart, pulsa «Choose SD card folder…».
   En PicoDex, pulsa «Abrir tarjeta SD». En la ventana que se abre, elige la microSD entera, no una
   carpeta de dentro. Si el navegador te pide permiso para ver o cambiar archivos, acéptalo.
4. Descarga las portadas. En PicoCover, pulsa «Start Processing». En TwilightBoxart, elige
   «Pico Launcher» en «Launcher:» y pulsa «Scan and download». En PicoDex, abre «Carátulas» (así llama
   PicoDex a las portadas) y pulsa el botón con el número de las que faltan, como «Bajar 12 carátulas».
5. En Mac, borra primero los archivos `._` con el comando de
   [Pantalla negra en una DSi o una 3DS, con un Mac](problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac).
   Después, en Windows o en Mac, expulsa la microSD antes de sacarla de la computadora, como en
   [El primer arranque](primeros-pasos.md#el-primer-arranque).
6. Mete la microSD en el cartucho y enciende la consola. Las portadas salen en la pantalla de arriba o,
   en Coverflow, en la de abajo.

Si en el paso 3 eliges una carpeta de dentro, como `ROMs`, PicoCover y TwilightBoxart guardan las
portadas en `ROMs/_pico/covers`, y Pico Launcher no las ve. Antes avisan: PicoCover con
«PicoLauncher Installation Not Detected» (pulsa «Cancelar» y elige otra vez) y TwilightBoxart con
«doesn't look like a supported launcher card». PicoDex no sigue: dice que no encuentra la carpeta
`/_pico`. Si ya te pasó, repite los pasos con la microSD entera y después borra la carpeta `_pico` que
quedó dentro de `ROMs`. La de la raíz no se toca.

Ninguna encuentra la portada de todos los juegos. PicoCover no encuentra la de algunas versiones europeas
de DS y de GBA, también españolas. Si a un juego le falta, prueba con otra herramienta o
[hazla tú](#hacer-tu-propia-portada). Y si cambias el nombre de un juego que tiene la portada en `user`,
cambia también el de la portada.

## Portadas de otras consolas

Pico Launcher no lee ningún código en los juegos de Game Boy, NES, Super Nintendo, Mega Drive y demás
consolas, así que su portada solo puede ir en `_pico/covers/user`, con el nombre completo del archivo más
`.bmp`: `Super Mario Land.gb.bmp` para `Super Mario Land.gb`. TwilightBoxart y PicoDex las ponen solas.

Si la pones a mano, la carpeta se llama `user`, no `users`, y las portadas van todas juntas, sin carpetas
por consola.

Los juegos de otras consolas solo salen en Pico Launcher si tienen una asociación con su emulador, como
explica [Otros emuladores](otros-emuladores.md). Su icono sigue siendo el genérico, tengan portada o no:
la 1.3.0 no deja cambiarlo.

## Hacer tu propia portada

Una portada es una imagen BMP de 256 colores y 128 por 96 píxeles. Solo se ven los 106 píxeles de la
izquierda: los 22 de la derecha quedan ocultos. Pico Launcher 1.3.0 no comprueba el formato, y si la
imagen no es exactamente así, la portada sale con píxeles de colores sueltos, con los colores cambiados o
boca abajo, sin avisar.

[Cover Creator](https://tasken.github.io/banner-maker/#cover) (en inglés) la hace en el navegador y deja
el BMP como lo pide Pico Launcher. La imagen no sale de tu computadora.

1. Abre Cover Creator, en la pestaña «Pico cover».
2. Arrastra la imagen al recuadro «Choose or drop a cover image here», o haz clic en él para buscarla.
   Sirve un PNG o un JPG, como una foto de la caja de tu juego. Elige cómo encaja: «Crop» para recortarla
   tú, «Fit» para verla entera con bandas a los lados o «Fill» para llenar toda la portada cortando los
   bordes.
3. En «Background», elige «Black» o «White»: es el color de las bandas y de lo transparente.
4. Deja «Dither» activado si es una foto o la imagen de una caja.
5. Pulsa «Download cover.bmp». Se descarga `cover.bmp`, normalmente en la carpeta Descargas.
6. Cámbiale el nombre: el nombre completo del archivo del juego, con su extensión, más `.bmp`, como
   `Super Mario Land.gb.bmp`. En Windows, ten las extensiones a la vista (en el Explorador de archivos,
   «Ver» > «Mostrar» > «Extensiones de nombre de archivo»; en Windows 10, pestaña «Vista»). Si no, el
   archivo queda como `Super Mario Land.gb.bmp.bmp` y Pico Launcher no lo encuentra.
7. Cópialo en `_pico/covers/user` de la microSD. Si no existe, crea `covers` dentro de `_pico` y `user`
   dentro de `covers`. Debajo del botón, Cover Creator dice que también puedes ponerlo dentro de una
   carpeta como `cover.bmp`: eso no funciona en Pico Launcher 1.3.0.
8. Termina como en los pasos 5 y 6 de
   [Poner portadas con una herramienta](#poner-portadas-con-una-herramienta).

## Si las portadas no salen o se ven mal

### No sale la portada

- La carpeta tiene que ser `_pico/covers/user`, `_pico/covers/nds` o `_pico/covers/gba`, en la
  [raíz](../glosario.md#raíz) de la microSD. Si tienes una carpeta `_pico` dentro de otra, como
  `ROMs/_pico`, Pico Launcher no la mira.
- En `user`, el nombre tiene que ser el del archivo del juego entero, extensión incluida, más `.bmp`. Las
  mayúsculas dan igual, salvo en las letras con tilde y la ñ: escríbelas igual que en el archivo del
  juego. En Windows, mira con las extensiones a la vista que no ponga `.bmp.bmp`.
- Tiene que ser un `.bmp`. Un `.png` o un `.jpg` no sale, aunque esté en la carpeta buena: hazlo con
  [Cover Creator](#hacer-tu-propia-portada).
- Los juegos de GBA solo salen en Pico Launcher si tienen la asociación con el emulador, y sin ella no
  hay portada. Lo explica [Juegos de GBA](gba.md#instalar-gbarunner3), que también tiene su apartado de
  [portadas](gba.md#portadas).
- Cada versión de un juego tiene su código: Pokémon Esmeralda es `BPEE` en EE. UU. y `BPES` en español,
  así que `BPEE.bmp` no sale en la versión española. Si no encuentras la portada de tu versión, ponla en
  `user` con el nombre del archivo.

### La portada se ve mal

El BMP no tiene el formato exacto que pide Pico Launcher (por ejemplo, tiene más de 256 colores), o es un
PNG o un JPG al que le cambiaron la extensión. Pico Launcher lo dibuja igual, y salen píxeles de colores
sueltos, otros colores o la imagen boca abajo. Hazla otra vez con
[Cover Creator](#hacer-tu-propia-portada) o descárgala con una de las tres herramientas.

### Sale la portada de otro juego

Un [ROM hack](../glosario.md#rom-hack) suele llevar el mismo código que el juego original, así que en
`nds` o `gba` le toca la portada del original. Ponle la suya en `user`, con el nombre de su archivo: la
de `user` gana.

## Instalar un tema

En noviembre de 2026 había más de 180 temas en la
[galería de temas de flashcarts.net](https://themes.flashcarts.net/pico/) (en inglés), con capturas de
cada uno. Pico Launcher ya trae dos, `material` (el de fábrica) y `raspberry`. Para ver el cambio sin
descargar nada, prueba los pasos 4 a 7 con `raspberry`.

Antes de empezar, mira que dentro de `_pico` esté `settings.json`. Si no está, mete la microSD en el
cartucho, enciende la consola hasta que salga Pico Launcher y apágala. Si ocultaste `_pico`, activa antes
en la computadora la opción de ver los elementos ocultos, como explica el final de
[Ocultar carpetas y archivos del menú](primeros-pasos.md#ocultar-carpetas-y-archivos-del-menú).

1. En la galería, abre el tema y, en «Downloads», pulsa el botón «Download …». Si hay varios, son
   variantes del mismo tema: elige una. Se descarga un archivo `.7z`.
2. Descomprímelo: en Windows 11, clic derecho en el archivo y «Extraer todo»; en Mac, doble clic. En
   Windows 10 hace falta [7-Zip](https://7-zip.org/): instálalo, haz clic derecho en el archivo y elige
   «7-Zip» > «Extraer aquí».
3. Busca la carpeta que tiene dentro el archivo `theme.json` y cópiala en la carpeta `_pico/themes` de la
   microSD, junto a `material` y `raspberry`. Fíjate que no quede dentro de otra carpeta: al descomprimir
   en Windows, a veces sale una carpeta con el nombre del tema y dentro otra igual. La que va en
   `_pico/themes` es la de dentro.
4. Guarda una copia de `_pico/settings.json` en la computadora: si algo sale mal, la pones encima.
   Después abre el de la microSD con el editor de texto, con clic derecho en el archivo: en Windows,
   «Abrir con» > «Bloc de notas» (si no sale, «Elegir otra aplicación»); en Mac, «Abrir con» >
   «TextEdit».
5. Busca la línea que empieza por `"theme"`. Si nunca cambiaste el tema, es esta:

   ```
   "theme": "material",
   ```

   Cambia solo lo que va entre las segundas comillas (`material`, o el tema que pusiste antes) por el
   nombre de la carpeta del tema, escrito igual. La página del tema en la galería te dice ese nombre (en
   inglés, «you will find a folder called …»). Deja las comillas y la coma. Por ejemplo, para el tema
   Altimit Pico OS:

   ```
   "theme": "Altimit Pico OS",
   ```

6. Guarda el archivo. En Mac, borra los archivos `._` con el comando de
   [Pantalla negra en una DSi o una 3DS, con un Mac](problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac).
   Después, en Windows o en Mac, expulsa la microSD antes de sacarla, como en
   [El primer arranque](primeros-pasos.md#el-primer-arranque). Si la sacas sin expulsarla,
   `settings.json` puede quedar a medias, y entonces Pico Launcher lo cambia por uno nuevo.
7. Mete la microSD en el cartucho y enciende la consola.

Algunos temas están pensados para una vista concreta. Si se ve raro, cambia la vista en
«Display Settings», como en [Dónde salen las portadas](#dónde-salen-las-portadas). Para volver al tema de
fábrica, pon otra vez `material`.

Si el tema trae música de fondo, va en una carpeta `bgm` dentro de la del tema. Si no la quieres, cambia
el nombre de esa carpeta, por ejemplo a `bgm-no`.

## Modo oscuro del tema de fábrica

El tema de fábrica, `material`, tiene modo claro y modo oscuro. Solo se ve si en `settings.json` está
puesto `"theme": "material",`.

1. Abre `_pico/themes/material/theme.json` con el editor de texto, como `settings.json` en el paso 4 de
   [Instalar un tema](#instalar-un-tema).
2. Cambia `"darkTheme": false` por `"darkTheme": true` y guarda.
3. Termina como en los pasos 6 y 7 de [Instalar un tema](#instalar-un-tema).

En el mismo archivo, los tres números de `primaryColor` son el color del tema: rojo (`r`), verde (`g`) y
azul (`b`), de 0 a 255. Si los cambias, cambia el color.

Cuando actualices Pico Launcher, la carpeta `material` se reemplaza por la nueva, como dice el paso 2 de
[Actualizar](primeros-pasos.md#actualizar), y vuelven el modo claro y el color de fábrica. Cambia otra
vez lo que hubieras tocado.

## Si el tema no cambia o vuelve al de fábrica

Si sale el tema de fábrica, mete la microSD en la computadora y abre otra vez `settings.json`:

- Si la línea `"theme"` sigue con el nombre de tu tema, Pico Launcher no encontró el tema y no avisa.
  Mira que `theme.json` esté justo dentro de `_pico/themes/NOMBRE`, sin otra carpeta en medio, y que
  `NOMBRE` sea lo mismo que pusiste en `settings.json`.
- Si vuelve a poner `material`, Pico Launcher no pudo leer el archivo y lo cambió por uno nuevo, sin
  avisar. Pasa por una comilla o una coma de más o de menos. Con eso también se borran tus asociaciones
  de emuladores, como la de GBARunner3. Pon encima la copia que guardaste en el paso 4 y vuelve a cambiar
  la línea del tema. Si no tienes copia, repite los pasos 4 a 7 y vuelve a poner tus asociaciones con
  [Juegos de GBA](gba.md#si-settingsjson-vuelve-a-como-estaba) u
  [Otros emuladores](otros-emuladores.md#las-asociaciones).

Si los textos no se leen o la portada sale fuera de lugar, puede que el tema esté hecho para Pico
Launcher 1.3.0 y tú tengas una versión anterior. [Actualiza Pico Launcher](primeros-pasos.md#actualizar).

Si se queda en la imagen del DSpico al encender y el tema tiene música, mira
[Se queda en la imagen del DSpico](problemas.md#se-queda-en-la-imagen-del-dspico).

## Hacer tu propio tema

El [Theme Creator](https://santiagovalencia109.github.io/pl-Theme-Creator/) hace un tema en el navegador:
subes una imagen para cada pantalla, colocas los textos y la portada arrastrándolos sobre una vista
previa y, si quieres, añades música desde un `.mp3`, un `.wav` o un `.ogg`. Está en inglés, aunque el zip
que genera trae las instrucciones de instalación también en español. Lo hizo Santiago Valencia, de
Colombia.

1. Escribe el nombre de tu tema en lugar de «My Awesome Theme»: así se llamarán el zip y la carpeta.
   Comprueba también que en «Versión» pone «v1.3.0».
2. Sube las imágenes con «Upload Top Screen» (la pantalla de arriba) y «Upload Bottom Screen (Touch)» (la
   de abajo). Se recortan a 256 por 192 píxeles, el tamaño de cada pantalla.
3. Coloca los textos y la portada en la vista previa.
4. Si quieres música, súbela en «Background Music (OPTIONAL)», con «Upload Audio». Un usuario aconseja
   que no dure más de 2 minutos y medio: mira
   [Se queda en la imagen del DSpico](problemas.md#se-queda-en-la-imagen-del-dspico).
5. Pulsa «Generate Full Theme (.zip)».
6. Descomprime el zip: en Windows, clic derecho y «Extraer todo»; en Mac, doble clic. Queda una carpeta
   con el nombre del tema y sus archivos dentro: es la carpeta del tema. Sigue desde el paso 3 de
   [Instalar un tema](#instalar-un-tema).

## Fuentes

Esta página se basa en la documentación de [Pico Launcher](https://github.com/LNH-team/pico-launcher)
sobre portadas, temas y ajustes, y en su código de la versión 1.3.0; en los apartados «Game Covers» y
«Themes» de la
[guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/); en la página
de cada herramienta: [PicoCover](https://github.com/Scaletta/PicoCover),
[TwilightBoxart](https://github.com/KirovAir/TwilightBoxart),
[PicoDex](https://github.com/rasalopa/picodex), [Cover Creator](https://github.com/tasken/banner-maker) y
[Theme Creator](https://github.com/santiagovalencia109/pl-Theme-Creator); y en las instrucciones de la
[galería de temas](https://github.com/flashcarts/kernel-themes). También usa casos de usuarios en
r/DsPico y r/flashcarts. Casi todas están en inglés.
