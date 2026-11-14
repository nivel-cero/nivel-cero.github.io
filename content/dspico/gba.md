---
title: "Juegos de GBA"
BookIcon: mando
weight: 35
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1", "GBARunner3 «hicode» del 25 de mayo de 2026"]
reviewed: 2026-11-10
---

Con el DSpico también se pueden abrir juegos de Game Boy Advance (GBA). El juego es un archivo `.gba` en
la microSD, y lo abre un programa que también va en la microSD, GBARunner3. No hace falta ningún cartucho
de GBA. Aquí no se dice dónde conseguir juegos ni el BIOS de la GBA.

En esta página, «DSi» incluye la DSi XL, y «3DS» incluye la 2DS y los modelos XL y New.

## Cómo funciona

La DS y la DS Lite abren juegos de GBA con un cartucho de GBA en la ranura de abajo. El DSpico va en la
de arriba, la de DS, y la DSi y la 3DS no tienen ranura de GBA. Por eso hace falta un programa.

GBARunner3 no imita la GBA instrucción por instrucción. Hace que el procesador principal de la DS ejecute
directamente el código del juego, y corrige sobre la marcha lo que la DS hace distinto. Por eso muchos
juegos van a su velocidad, pero algunos van a tirones o tienen fallos de sonido. Su autor lo achaca
sobre todo a esas correcciones, al sonido y a las lecturas de la microSD.

Al abrir un juego, GBARunner3 copia en la memoria de la consola sus primeros 2 MB, y el resto lo va
leyendo de la microSD mientras juegas. Por eso aquí la microSD también cuenta: una tarjeta lenta, falsa o
con los archivos [muy partidos](../glosario.md#archivo-partido-en-trozos) se nota en forma de tirones.

El DSpico no hace la consola más potente. Lo que cambia es que en una DSi o una 3DS abre GBARunner3 en
modo DSi, que es más rápido, y los demás cartuchos que se venden hoy, como las R4, lo abren en modo DS:
lo explica [En una DS, una DSi o una 3DS](#en-una-ds-una-dsi-o-una-3ds).

GBARunner3 es de Gericom, que también es el autor principal de Pico Launcher. No tiene ninguna versión
oficial publicada, y su código no cambia desde junio de 2025. Lo que usa la gente es un
`GBARunner3.nds` que preparó otra persona con la versión «hicode», una variante que Gericom tiene aparte
de la principal, y que enlaza la guía de emuladores de Sanrax. Es el que explica esta página. La versión
«hicode» sabe ejecutar el código del juego que pasa de esos primeros 2 MB, y sin ella no arranca, por
ejemplo, Pokémon Esmeralda.

Hay juegos que solo van con el anterior, [GBARunner2](#gbarunner2), que no se actualiza desde 2020.

## Qué necesitas

- GBARunner3, de la
  [guía de emuladores de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/emulators-pico/)
  (en inglés).
- El [BIOS](../glosario.md#bios) de la GBA, el programa que la GBA lleva grabado de fábrica, copiado en
  un archivo de 16 KB. Sin él, GBARunner3 no funciona, y no avisa. Esta guía no lo enlaza.
- Haber abierto Pico Launcher al menos una vez. Así se crea el archivo `_pico/settings.json`, que hay
  que cambiar. Si no lo ves dentro de `_pico`, mete la microSD en el cartucho, enciende la consola hasta
  que salga Pico Launcher y apágala. Si ocultaste `_pico`, activa antes en la computadora la opción de
  ver los elementos ocultos, como explica el final de
  [Ocultar carpetas y archivos del menú](primeros-pasos.md#ocultar-carpetas-y-archivos-del-menú).
- Un editor de texto en la computadora: el Bloc de notas en Windows o TextEdit en Mac.

## Instalar GBARunner3

En Windows, antes de empezar, haz que se vean las extensiones (`.bin`, `.json`): en el Explorador de
archivos, «Ver» > «Mostrar» > «Extensiones de nombre de archivo» (en Windows 10, pestaña «Vista»). Si no,
un archivo puede quedarse con dos, como `bios.bin.bin`, y GBARunner3 no lo encuentra.

1. En la guía de Sanrax, abre la pestaña «GBA» y, dentro de ella, «GBARunner3». Pulsa el enlace del
   primer paso, «GBARunner3 zip file.», y se descarga `GBARunner3-hicode.zip`. Descomprímelo: en Windows,
   clic derecho en el zip y «Extraer todo»; en Mac, doble clic. Queda una carpeta, `GBARunner3-hicode`,
   que no se copia a la microSD. Dentro hay un archivo, `GBARunner3.nds`, y una carpeta, `_gba`.
2. Copia la carpeta `_gba` en la raíz de la microSD, junto a `_pico` y no dentro de ella. Si ya tienes
   una carpeta `_gba`, por ejemplo con el BIOS de GBARunner2, copia dentro de ella solo la carpeta
   `configs` del zip: en Mac, si copias `_gba` entera, el Finder reemplaza la tuya y borra lo que tenía.
3. Pon el BIOS dentro de `_gba` y cámbiale el nombre a `bios.bin`. Si Windows avisa de que cambias la
   extensión, pulsa «Sí».
4. Dentro de `_pico`, crea una carpeta llamada `emulators`, en inglés, y copia en ella `GBARunner3.nds`.
5. Abre `_pico/settings.json` con el editor de texto, con clic derecho en el archivo: en Windows,
   «Abrir con» > «Bloc de notas» (si no sale, «Elegir otra aplicación»); en Mac, «Abrir con» >
   «TextEdit». La última línea antes de la llave final es esta:

   ```
   "fileAssociations": {}
   ```

   Selecciónala entera y pega encima este bloque, copiado de aquí y no escrito a mano. Es la asociación:
   le dice a Pico Launcher que abra los archivos `.gba` con GBARunner3.

   ```
   "fileAssociations": {
     "gba": {
       "appPath": "/_pico/emulators/GBARunner3.nds"
     }
   }
   ```

   Al final del archivo tienen que quedar tres llaves de cierre, `}`, cada una en su línea. Si en vez de
   esa línea ves `"fileAssociations": {` y debajo más líneas, es que ya tienes otro emulador: mira
   [Si ya tienes otro emulador](#si-ya-tienes-otro-emulador).
6. Guarda el archivo. Copia tus juegos `.gba` en la carpeta de la microSD que quieras, por ejemplo
   `ROMs/GBA`. Los nombres con tildes o eñes valen.
7. En Mac, borra primero los archivos `._` con el comando de
   [Pantalla negra en una DSi o una 3DS, con un Mac](problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac).
   Después, expulsa la microSD antes de sacarla de la computadora, como en
   [El primer arranque](primeros-pasos.md#el-primer-arranque). Si la sacas sin expulsarla,
   `settings.json` puede quedar a medias, y entonces Pico Launcher lo cambia por uno nuevo.
8. Mete la microSD en el cartucho y enciende la consola. En Pico Launcher, los `.gba` salen con el icono
   de la GBA. Ábrelos como un juego de DS.

Así queda la microSD, además de lo que ya tenía, como `_picoboot.nds` y los archivos de Pico Loader. Lo
que acaba en `/` es una carpeta, y lo que va más a la derecha está dentro de la carpeta de encima:

```
_gba/
    bios.bin
    configs/
_pico/
    emulators/
        GBARunner3.nds
    settings.json
ROMs/
    GBA/
        Juego.gba
```

No hace falta abrir `GBARunner3.nds`. No tiene menú, y si lo abres solo, busca un juego llamado
`rom.gba` en la raíz de la microSD.

## Si ya tienes otro emulador

Cada asociación va separada de la siguiente con una coma, y la última no lleva coma. Por ejemplo, si
además tienes nesDS para la NES:

```
"fileAssociations": {
  "gba": {
    "appPath": "/_pico/emulators/GBARunner3.nds"
  },
  "nes": {
    "appPath": "/_pico/emulators/nesDS.nds"
  }
}
```

Cada extensión solo puede tener un programa. La ruta de `appPath` puede empezar por `/` o por `fat:/`:
valen las dos. Para los emuladores de otras consolas, [Otros emuladores](otros-emuladores.md) tiene un
bloque con todas las asociaciones, también la de GBA.

## Si `settings.json` vuelve a como estaba

Si después de cambiarlo los `.gba` no salen, mete la microSD en la computadora y abre otra vez
`settings.json`. Si vuelve a poner `"fileAssociations": {}`, Pico Launcher no pudo leer el archivo y lo
cambió por uno nuevo, sin avisar. Si habías elegido otro tema, también vuelve el de fábrica. Pasa por una
coma o una llave de más o de menos, o por un comentario con `//`.

Para arreglarlo, si guardaste una copia del archivo cuando funcionaba, cópiala encima. Si no, vuelve a
hacer el paso 5 de [Instalar GBARunner3](#instalar-gbarunner3), copiando el bloque de esta página.

Pico Launcher vuelve a escribir `settings.json` cada vez que abres un juego. Guarda sus propios ajustes,
entre ellos las asociaciones, pero si añades a mano otra opción que no es suya, la borra. Guarda una
copia del archivo en la computadora cuando te funcione.

## Si un juego no arranca

- Los `.gba` no salen en Pico Launcher. Si tus juegos están dentro de un `.zip` o un `.7z`,
  descomprímelos antes, porque Pico Launcher no muestra los comprimidos. Si no es eso, falta la
  asociación o `settings.json` volvió a como estaba: mira el apartado de arriba.
- Sale «Failed to open the rom file.» y debajo `fat:/_pico/emulators/GBARunner3.nds`. GBARunner3 no está
  en la ruta que dice `appPath`. Comprueba en la computadora que `GBARunner3.nds` está dentro de
  `_pico`, en una carpeta llamada `emulators` (en inglés, no «emuladores»), y no en la raíz ni en la
  carpeta que salió del zip. Lo explica también
  [«Failed to open the rom file.»](problemas.md#failed-to-open-the-rom-file), en «Problemas».
- Todos los juegos se quedan en negro. Revisa el BIOS: tiene que llamarse `bios.bin` (en Windows, con
  las extensiones a la vista, que no ponga `bios.bin.bin`), estar en `_gba` y medir 16 KB. El tamaño se
  ve en Windows con clic derecho y «Propiedades», y en Mac con «Archivo» > «Obtener información».
  GBARunner3 no lo comprueba, así que si falta o está dañado no sale ningún mensaje. A un usuario con el
  BIOS dañado se le quedaban todos los juegos en negro, y se le arregló con una copia buena.
- La pantalla se queda azul. GBARunner3 la pone así cuando no puede leer la microSD, pero a un usuario
  con DSpico le pasaba con una tarjeta que GBARunner2 sí leía, y en r/flashcarts le contestaron que
  suele ser el BIOS. Revisa primero el BIOS, como en el punto anterior. Si está bien, copia todo a la
  computadora, formatea la microSD con los pasos de [La microSD](primeros-pasos.md#la-microsd), aunque
  ya esté en FAT32, y vuelve a copiarlo. A un usuario al que se le congelaba al arrancar, con un cuadro
  azul moviéndose por la pantalla del título, se le arregló formateando la tarjeta entera. Si sigue
  igual, prueba con otra microSD, de marca y original.
- Un juego se queda en blanco después del logo de la GBA, y los demás van bien. Si es Pokémon
  Esmeralda, mira [Pokémon Esmeralda](#pokémon-esmeralda). Si es un ROM hack, mira
  [Juegos que fallan](#juegos-que-fallan). Si es otro juego, prueba con [GBARunner2](#gbarunner2).
  También puede ser que tu copia del juego esté mal: a un usuario, la Esmeralda italiana no le arrancaba
  aunque ya tenía su archivo de ajustes, y era porque su copia tenía un error.

## Pokémon Esmeralda

Pokémon Esmeralda en español se queda en blanco después del logo de la GBA. GBARunner3 trae en
`_gba/configs` archivos de ajustes para juegos concretos, uno por cada versión, y cada archivo lleva el
código de cuatro letras del juego, que cambia con el idioma: `BPEE` es Esmeralda en inglés y `BPES`, en
español. De Esmeralda solo trae el de la versión en inglés, `BPEE00.json`. Para la española falta
`BPES00.json`. Se arregla así:

1. En la computadora, abre la carpeta `_gba/configs` de la microSD.
2. Haz una copia de `BPEE00.json` en la misma carpeta: en Windows, selecciónalo y pulsa Ctrl+C y después
   Ctrl+V; en Mac, clic derecho y «Duplicar». La copia sale con la palabra «copia» en el nombre.
3. Cámbiale el nombre a la copia para que quede exactamente `BPES00.json`: en Windows, selecciónala y
   pulsa F2; en Mac, selecciónala y pulsa Retorno. En Windows, ten las extensiones a la vista, como dice
   [Instalar GBARunner3](#instalar-gbarunner3): si no, puede quedar como `BPES00.json.json`, y no sirve.

Lo probamos con la española y, en una DS Lite, con la italiana. Con la italiana, el archivo es
`BPEI00.json`. También faltan los de la francesa, la alemana y la japonesa, pero nadie ha contado todavía
si con ellas funciona lo mismo.

Rubí, Zafiro, Rojo Fuego y Verde Hoja sí traen su archivo en cada idioma, también en español.

En una DSi, a un usuario se le queda colgado Esmeralda al reiniciar el juego pulsando A, B, START y
SELECT a la vez (lo que se llama *soft reset*), y Rojo Fuego no. Si te pasa, apaga la consola.

## Juegos que fallan

Muchos ROM hacks modernos de Esmeralda, los que se hacen a partir de su código reconstruido (en inglés,
*decomp*), se quedan en blanco. Según la persona que propuso un arreglo en la página de GitHub de
GBARunner3, los que usan Emerald Expansion llevan el mismo código de cuatro letras que Esmeralda,
`BPEE`, así que GBARunner3 les aplica los ajustes de `BPEE00.json`, que a ellos ya no les sirven, y
además guardan de una forma que GBARunner3 no reconoce. Nadie del proyecto ha revisado ese arreglo, y no
está en la versión que enlaza Sanrax.

Según usuarios de Reddit y de la página de GitHub de GBARunner3, Emerald Seaglass y Lazarus se quedan en
blanco, Unbound se cuelga al entrar en un combate, ROWE falla al entrar en un combate, Elite Redux no
pasa de la pantalla inicial e Inclement Emerald puede colgarse. Un usuario con DSpico calcula que le
falla uno de cada tres hacks de Pokémon, y que los juegos sin modificar le van bien.

Juegos sin modificar con fallos conocidos en GBARunner3:

- Según un usuario, Golden Sun se cuelga al usar una invocación, y Golden Sun: La Edad Perdida al usar
  psinergías. Otro avisó de fallos de sonido en el primer Golden Sun.
- Dr. Mario & Puzzle League no guarda la partida, y al elegir Dr. Mario el juego se cuelga.

Si un juego falla, prueba con GBARunner2. Según un usuario, Fire Emblem: The Binding Blade solo le va en
GBARunner2, y al revés, The Legend of Zelda: The Minish Cap tiene en GBARunner2 un fallo grave que en
GBARunner3 no tiene. Otro hizo funcionar Boktai 2 y 3 con parche en GBARunner2, con algunos fallos
gráficos, después de que no le fueran en GBARunner3.

## GBARunner2

GBARunner2 es el programa anterior de Gericom. La guía de Sanrax enlaza una versión mejorada por otra
persona, «DSL Enhanced», que es un solo archivo: `GBARunner2_arm9dldi_ds.nds`. Vale también en una DSi y
en una 3DS. Las versiones de Gericom traen también un archivo que termina en `_3ds`: no lo uses, porque
con el DSpico la 3DS funciona como una DSi.

Con GBARunner2 el BIOS es opcional. Si no lo encuentra, usa uno libre que lleva dentro, aunque algunos
juegos van mejor con el de verdad. Lo busca, entre otros sitios, en `_gba/bios.bin`, así que sirve el
mismo que pusiste para GBARunner3. Si el archivo no mide 16 KB, se para con el mensaje «Bios invalid!».

Como cada extensión solo puede tener un programa, los `.gba` no se pueden abrir con los dos. Deja
GBARunner3 en `settings.json` y abre GBARunner2 a mano cuando lo necesites:

1. En la guía de Sanrax, abre la pestaña «GBA» y, dentro de ella, «GBARunner2». Pulsa el enlace del
   primer paso, «Download DSL Enhanced GBARunner2.». Se descarga el archivo tal cual, sin zip.
2. Cópialo en la carpeta `_pico/emulators` de la microSD, junto a `GBARunner3.nds`. Si ocultaste
   `_pico`, Pico Launcher no muestra esa carpeta: cópialo en la raíz.
3. En Pico Launcher, entra en la carpeta donde lo pusiste y ábrelo como un juego de DS.
4. Elige el juego en su propia lista, que empieza en la raíz de la microSD, o en la carpeta `gba` si hay
   una en la raíz. Si tus juegos están en `ROMs/GBA`, entra en `ROMs` y después en `GBA`.

## Partidas

GBARunner3 guarda la partida junto al juego, con el mismo nombre y la extensión `.sav`: `Juego.gba`
guarda en `Juego.sav`. Si no existe, la crea.

GBARunner3 no escribe la partida en la microSD en el mismo momento con todos los juegos: depende de la
memoria en que guarda cada uno. Con muchos, como los Pokémon, la escribe en el momento de guardar. Con
otros, la escribe un momento después en una DS o una DS Lite, pero en una DSi solo cuando pulsas POWER:
una pulsación corta reinicia la consola y una larga la apaga, y en los dos casos GBARunner3 escribe antes
la partida. La 3DS también funciona en modo DSi, así que tampoco la escribe sola, y nadie ha comprobado
todavía si al pulsar POWER la escribe. Como desde fuera no se ve qué hace cada juego, en una DSi o una
3DS sal siempre con POWER. En una DS o una DS Lite, espera unos segundos después de guardar antes de
apagar.

GBARunner3 no tiene estados de guardado: solo vale guardar dentro del juego. Haz copias de tus `.sav` en
la computadora de vez en cuando.

## Pantalla de abajo, colores y marco

GBARunner3 no tiene menú de opciones. Se configura con un archivo de texto que tienes que crear tú,
`_gba/gbarunner3.json`. Si tiene un error, GBARunner3 no lo usa y no avisa.

Para crearlo, copia el texto de uno de los ejemplos de abajo y pégalo en un archivo nuevo, sin escribirlo
a mano:

- En Windows, abre el Bloc de notas, pega el texto y elige «Archivo» > «Guardar como». Ve a la carpeta
  `_gba` de la microSD, en «Tipo» elige «Todos los archivos (\*.\*)», escribe el nombre `gbarunner3.json`
  y pulsa «Guardar».
- En Mac, abre TextEdit, crea un documento nuevo y elige «Formato» > «Convertir a texto normal» antes de
  pegar: si no, TextEdit lo guarda con formato y GBARunner3 no lo entiende. Pega el texto, guárdalo en la
  carpeta `_gba` de la microSD con el nombre `gbarunner3.json` y, si pregunta qué extensión usar, elige
  `.json`.

Por defecto, el juego sale en la pantalla de arriba. Este ejemplo lo pone en la de abajo, cambia los
colores y se salta la animación del BIOS de la GBA. Las opciones van separadas por comas:

```
{
  "displaySettings": {
    "gbaScreen": "bottom",
    "gbaColorCorrection": "ags101"
  },
  "runSettings": {
    "skipBiosIntro": true
  }
}
```

- `gbaScreen` en `"bottom"` pone el juego en la pantalla de abajo. La animación de arranque de
  GBARunner3 sale siempre arriba, y la opción de la configuración de la DS y la DS Lite que elige la
  pantalla de los juegos de GBA no le afecta.
- `gbaColorCorrection` cambia los colores para que se parezcan a los de otra pantalla: `"agb001"` para la
  GBA original, `"ags101"` para la GBA SP con luz. Por defecto es `"none"`.
- `skipBiosIntro` en `true` se salta la animación del BIOS de la GBA al abrir un juego.
- `borderImage` en `"none"` no muestra tu imagen de marco, y el borde queda negro. Va dentro de
  `displaySettings`, como `gbaScreen`.

La imagen sale a su tamaño, 240 por 160 píxeles, en el centro de la pantalla de la DS, que mide 256 por
192. No se puede ampliar ni ponerle filtros. Lo que queda alrededor es negro, o una imagen tuya: un BMP
de 256 por 192 píxeles y 256 colores, sin comprimir. Si se llama `_gba/border.bmp`, sale en todos los
juegos. Si va en la carpeta `_gba/borders` con el código del juego, como `BPES.bmp`, sale solo en ese.

Los archivos de `_gba/configs` son ajustes para juegos concretos que ya trae GBARunner3. No los cambies,
salvo para lo de [Pokémon Esmeralda](#pokémon-esmeralda).

## Lo que GBARunner3 no hace

- No vuelve al menú. Para salir hay que reiniciar o apagar la consola.
- No tiene estados de guardado, trucos ni modo reposo al cerrar la tapa.
- No deja cambiar los botones.
- No imita el reloj de los cartuchos que lo llevan, como los de Pokémon Rubí, Zafiro y Esmeralda, ni el
  sensor de luz solar de Boktai. El reloj ya está hecho en una versión en pruebas de GBARunner3, pero
  todavía no está en la que enlaza Sanrax.
- No usa la ranura de GBA: no abre cartuchos de GBA ni usa el Memory Expansion Pak.

Casi todo eso está pedido en su página de GitHub, pero su código no cambia desde junio de 2025.

## En una DS, una DSi o una 3DS

En una DS o una DS Lite, GBARunner3 funciona en [modo DS](../glosario.md#modo-ds), con el procesador
principal a 67 MHz. En una DSi o una 3DS funciona en [modo DSi](../glosario.md#modo-dsi) y lo sube a
134 MHz, salvo en unos pocos juegos cuyos ajustes de `_gba/configs` lo dejan a 67 MHz porque así van
mejor. Por eso algunos juegos cambian de una consola a otra: según Dartz150, que colabora en GBARunner3,
Mega Man Zero 4 se ralentiza en algunas escenas en modo DS y en modo DSi va bien.

Las versiones antiguas de GBARunner3 se quedaban en blanco en una DSi sin tarjeta SD en su propia ranura.
La que enlaza Sanrax ya no la necesita, porque lee la microSD del DSpico. Otros emuladores sí la
necesitan: lo cuenta
[Un emulador se queda en blanco o colgado en una DSi](problemas.md#un-emulador-se-queda-en-blanco-o-colgado-en-una-dsi),
en «Problemas».

## Portadas

Pico Launcher puede poner portada a los juegos de GBA. Hay dos sitios para ella:

- En `_pico/covers/gba/`, con el código del juego, como `BPES.bmp` para Pokémon Esmeralda en español.
- En `_pico/covers/user/`, con el nombre completo del archivo del juego, como
  `Pokémon Esmeralda.gba.bmp`. Si hay portada en los dos sitios, sale esta.

El código está en el número de serie de la etiqueta del cartucho y de la caja: en `AGB-BPES-ESP` es
`BPES`. Cada versión tiene el suyo, así que una portada con el código de la versión de EE. UU. (`BPEE`)
no sale en la española. Si no sabes el código, usa la segunda forma, con el nombre del archivo.

Tiene que ser un BMP de 256 colores y 128 por 96 píxeles, del que solo se ven los 106 píxeles de la
izquierda. Pico Launcher 1.3.0 no deja poner iconos ni títulos propios a los juegos de GBA; la próxima
versión, en la que trabaja el LNH Team, ya los lee.

## Fuentes

Esta página se basa en el código, las issues y el documento técnico de
[GBARunner3](https://github.com/Gericom/GBARunner3), en [GBARunner2](https://github.com/Gericom/GBARunner2)
y su versión [DSL Enhanced](https://github.com/unresolvedsymbol/GBARunner2-DSL-Enhanced), en la
documentación de [Pico Launcher](https://github.com/LNH-team/pico-launcher) sobre asociaciones y
portadas, y en la
[guía de emuladores de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/emulators-pico/).
También usa casos de usuarios en r/flashcarts, r/DsPico, r/nds y r/NDSHacks, y lo que probamos con una
DS Lite. Casi todas están en inglés.
