---
title: "Otros emuladores"
BookIcon: palanca
weight: 37
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1"]
reviewed: 2026-11-12
---

Con el DSpico también se pueden abrir juegos de otras consolas, como la Game Boy, la Super Nintendo o la
Mega Drive. Para cada consola hace falta un [emulador](../glosario.md#emulador), un programa de DS que va
en la microSD y que Pico Launcher abre por su cuenta cuando eliges un juego de esa consola. Los juegos de
GBA tienen su propia página, [Juegos de GBA](gba.md). Aquí no se dice dónde conseguir juegos ni BIOS.

En esta página, «DSi» incluye la DSi XL, y «3DS» incluye la 2DS y los modelos XL y New.

## Qué consolas se pueden jugar

Estas son las consolas de la
[guía de emuladores de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/emulators-pico/) (en
inglés). La columna «Extensiones» dice cómo acaba el nombre de los juegos de cada consola, y la del
[BIOS](../glosario.md#bios), si el emulador lo necesita.

| Consola | Emulador | Extensiones | BIOS |
|---|---|---|---|
| Game Boy y Game Boy Color | GameYob | `.gb`, `.gbc` | No |
| Super Nintendo | SNEmulDS | `.sfc`, `.smc` | No |
| NES | nesDS | `.nes` | No |
| Mega Drive y Genesis | jEnesisDSPlus | `.gen`, `.smd` | No |
| Master System y Game Gear | S8DS | `.sms`, `.gg`, `.sg`, `.sc` | Opcional |
| Neo Geo Pocket y Pocket Color | NGPDS | `.ngp`, `.ngc` | Solo para guardar |
| PC Engine y TurboGrafx-16 | NitroGrafx | `.pce`, `.iso`, `.cue` | Solo los CD |
| Atari 2600 | StellaDS | `.a26` | No |
| Atari 5200 | A5200DS | `.a52` | Opcional |
| Atari 7800 | A7800DS | `.a78` | Opcional |
| Atari 800 y 400 | A8DS | `.car`, `.xex`, `.atr`, `.atx` | Opcional |
| ColecoVision | ColecoDS | `.col` y 11 más | Sí |
| Intellivision | NINTV-DS | `.int` | Sí |
| Neo Geo | NeoDS | `.neo`, sin asociación | Para convertir los juegos |

No se pueden abrir juegos de 3DS, ni siquiera en una 3DS: el DSpico solo abre programas de DS y de DSi.
La guía de Sanrax tampoco tiene emuladores de PlayStation, Nintendo 64 ni GameCube.

El DSpico no hace la consola más potente. En una DS o una DS Lite, un emulador va igual que con otro
cartucho. En una DSi o una 3DS, Pico Loader abre casi todos en modo DSi, que es más rápido, y los demás
cartuchos que se venden hoy, como las R4, los abren en modo DS: lo explica
[En una DS, una DSi o una 3DS](#en-una-ds-una-dsi-o-una-3ds).

## Cómo funciona

Pico Launcher muestra en su lista los juegos de DS y, de los demás archivos, solo los que tienen una
asociación: una línea en el archivo `_pico/settings.json` que dice con qué emulador se abre cada
extensión. Si una extensión no tiene asociación, sus juegos no salen en la lista, aunque estén en la
microSD.

Cuando eliges un juego, Pico Launcher abre el emulador y le pasa la [ruta](../glosario.md#ruta) del juego,
y el emulador lo carga sin pasar por su lista de juegos. Cada extensión puede tener un solo emulador.
NeoDS no sabe recibir la ruta así, y por eso se abre a mano.

## Qué necesitas

- El emulador de cada consola, de la
  [guía de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/emulators-pico/), en la pestaña
  de esa consola.
- El BIOS de las consolas que lo piden en la tabla, si quieres abrir sus juegos. Esta guía no los enlaza.
- Haber abierto Pico Launcher al menos una vez, para que exista `_pico/settings.json`. Si no lo ves dentro
  de `_pico`, mete la microSD en el cartucho, enciende la consola hasta que salga Pico Launcher y apágala.
  Si ocultaste `_pico`, activa antes en la computadora la opción de ver los elementos ocultos, como
  explica el final de
  [Ocultar carpetas y archivos del menú](primeros-pasos.md#ocultar-carpetas-y-archivos-del-menú).
- Un editor de texto en la computadora: el Bloc de notas en Windows o TextEdit en Mac.
- En Windows, ver las extensiones de los archivos: en el Explorador de archivos, «Ver» > «Mostrar» >
  «Extensiones de nombre de archivo» (en Windows 10, pestaña «Vista»). Si no, al cambiar la extensión de
  un juego puede quedar con dos, como `Juego.gen.md`, y Pico Launcher no lo muestra.

## Las asociaciones

Se hace una sola vez. Este bloque asocia cada extensión de la tabla, menos la de Neo Geo, con su emulador
en `_pico/emulators`, y también los `.gba` con GBARunner3. Si no tienes el emulador de una consola, su
línea no molesta mientras no tengas juegos de esa consola.

El bloque sustituye las asociaciones que ya tuvieras. Si alguna apuntaba a otro programa, como
`PicoDriveTWL.nds` o `GBARunner2_arm9dldi_ds.nds`, o a otra carpeta, cambia esa ruta en el bloque después
de pegarlo.

1. Guarda una copia de `_pico/settings.json` en la computadora.
2. Abre `_pico/settings.json` con el editor de texto, con clic derecho en el archivo: en Windows, «Abrir
   con» > «Bloc de notas» (si no sale, «Elegir otra aplicación»); en Mac, «Abrir con» > «TextEdit».
3. Haz clic justo antes de las comillas de la línea `"fileAssociations"` y selecciona desde ahí hasta el
   final del archivo, la última llave `}` incluida: en Windows, con Ctrl+Mayús+Fin; en Mac, con
   Comando+Mayúsculas+flecha abajo.
4. Pega encima este bloque, copiado de aquí y no escrito a mano:

   ```
   "fileAssociations": {
       "gba": { "appPath": "/_pico/emulators/GBARunner3.nds" },
       "gb": { "appPath": "/_pico/emulators/gameyob.nds" },
       "gbc": { "appPath": "/_pico/emulators/gameyob.nds" },
       "sfc": { "appPath": "/_pico/emulators/snemulds-shim.nds" },
       "smc": { "appPath": "/_pico/emulators/snemulds-shim.nds" },
       "nes": { "appPath": "/_pico/emulators/nesDS.nds" },
       "gen": { "appPath": "/_pico/emulators/jEnesisDSPlus.nds" },
       "smd": { "appPath": "/_pico/emulators/jEnesisDSPlus.nds" },
       "sms": { "appPath": "/_pico/emulators/S8DS.nds" },
       "gg": { "appPath": "/_pico/emulators/S8DS.nds" },
       "sg": { "appPath": "/_pico/emulators/S8DS.nds" },
       "sc": { "appPath": "/_pico/emulators/S8DS.nds" },
       "ngp": { "appPath": "/_pico/emulators/NGPDS.nds" },
       "ngc": { "appPath": "/_pico/emulators/NGPDS.nds" },
       "pce": { "appPath": "/_pico/emulators/NitroGrafx.nds" },
       "iso": { "appPath": "/_pico/emulators/NitroGrafx.nds" },
       "cue": { "appPath": "/_pico/emulators/NitroGrafx.nds" },
       "a26": { "appPath": "/_pico/emulators/StellaDS.nds" },
       "a52": { "appPath": "/_pico/emulators/A5200DS.nds" },
       "a78": { "appPath": "/_pico/emulators/A7800DS.nds" },
       "car": { "appPath": "/_pico/emulators/A8DS.nds" },
       "xex": { "appPath": "/_pico/emulators/A8DS.nds" },
       "atr": { "appPath": "/_pico/emulators/A8DS.nds" },
       "atx": { "appPath": "/_pico/emulators/A8DS.nds" },
       "col": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "cv": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "cas": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "com": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "ddp": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "dsk": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "mtx": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "msx": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "m5": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "pen": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "pv": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "pv1": { "appPath": "/_pico/emulators/ColecoDS.nds" },
       "int": { "appPath": "/_pico/emulators/NINTV-DS.nds" }
     }
   }
   ```

5. La línea de encima de `"fileAssociations"` tiene que acabar en coma, y al final del archivo tienen que
   quedar dos llaves de cierre, `}`, cada una en su línea. Guarda el archivo.

Pico Launcher vuelve a escribir `settings.json` cada vez que abres un juego, con su propio formato: es
normal que después cada asociación ocupe tres líneas. Cuando te funcione, guarda otra copia del archivo
en la computadora.

Si los juegos dejan de salir y el archivo vuelve a poner `"fileAssociations": {}`, Pico Launcher no pudo
leerlo y lo cambió por uno nuevo, sin avisar. Pasa por una coma o una llave de más o de menos. Pon encima
la copia que guardaste o repite estos pasos con el bloque de esta página. Si después instalas GBARunner3
con [Juegos de GBA](gba.md#instalar-gbarunner3), sáltate su paso 5: este bloque ya lleva la GBA.

## Instalar un emulador

Antes de empezar, lee el apartado de tu consola, más abajo: dice qué archivo usar, qué carpetas crear y si
hay que cambiar la extensión de los juegos. La Neo Geo no sigue estos pasos: mira [Neo Geo](#neo-geo).

Una ruta como `data/S8DS` es una carpeta `S8DS` dentro de una carpeta `data`, en la
[raíz](../glosario.md#raíz) de la microSD. Si no existen, créalas. La barra no va en ningún nombre.

1. En la guía de Sanrax, abre la pestaña de la consola y descarga el emulador con el enlace del primer
   paso. Algunas pestañas tienen otro nombre: la de Game Boy es «GB/C»; la de Mega Drive, «Sega
   Genesis/MegaDrive», y dentro de ella, «jEnesisDSPlus»; la de PC Engine, «PC-Engine/TurboGrafx-16».
2. GameYob, S8DS, NGPDS, NitroGrafx y el paquete de SNEmulDS vienen en un zip. Descomprímelo: en Windows,
   clic derecho en el zip y «Extraer todo»; en Mac, doble clic. Si sale una carpeta `__MACOSX`, no la
   copies: son [archivos `._` del Mac](../glosario.md#archivos-del-mac).
3. Dentro de `_pico`, crea una carpeta llamada `emulators`, en inglés, si no la tienes ya. Copia en ella
   el `.nds` del emulador.
4. Copia los juegos en la carpeta de la microSD que quieras, por ejemplo `ROMs/NES`. Si vienen dentro de
   un `.zip` o un `.7z`, descomprímelos antes: Pico Launcher no muestra los comprimidos. Mira también en
   la tabla que acaben con la extensión de su consola, porque algunos juegos de Mega Drive y de Atari
   vienen con otra. Para cambiarla, selecciona el archivo, pulsa F2 en Windows o Retorno en Mac y cambia
   solo lo que va después del punto. Si Windows avisa de que cambias la extensión, pulsa «Sí»; si el Mac
   pregunta, elige la nueva.
5. Crea las carpetas y pon el BIOS que pida el apartado de tu consola, si pide alguno.
6. Expulsa la microSD antes de sacarla de la computadora, como en
   [El primer arranque](primeros-pasos.md#el-primer-arranque): si la sacas sin expulsarla,
   `settings.json` puede quedar a medias, y entonces Pico Launcher lo cambia por uno nuevo. En Mac, antes
   de expulsarla, borra los archivos `._` con el comando de
   [Pantalla negra en una DSi o una 3DS, con un Mac](problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac).
7. Mete la microSD en el cartucho y enciende la consola. En Pico Launcher, abre la carpeta de los juegos
   y elige uno. Salen con un icono genérico, no con el de su consola.

Así queda la microSD con dos emuladores, el de NES y el de Mega Drive, además de lo que ya tenía. Lo que
acaba en `/` es una carpeta, y lo que va más a la derecha está dentro de la carpeta de encima:

```
_pico/
    emulators/
        jEnesisDSPlus.nds
        nesDS.nds
    settings.json
ROMs/
    Genesis/
        Juego.gen
    NES/
        Juego.nes
```

## Game Boy y Game Boy Color

GBARunner3 no abre juegos de Game Boy ni de Game Boy Color: para ellos hace falta GameYob.

Del zip de GameYob, usa `gameyob.nds`. El otro, `gameyob_dsi.nds`, es para abrirlo desde la tarjeta SD de
una DSi modificada, y con Pico Loader en una DSi o una 3DS da
[«Failed to load arm9i.»](problemas.md#failed-to-load-arm9i-y-failed-to-load-arm7i).

Los juegos de Game Boy Color salen en color sin el BIOS. Los de la Game Boy original salen en gris.

GameYob guarda la partida junto al juego, con la extensión `.sav`. Sus ajustes van en `gameyobds.ini`, en
la raíz de la microSD.

## Super Nintendo

El emulador es SNEmulDS, en la versión 0.6d de Coto, que lo sigue actualizando. Pico Launcher lo abre a
través de SNEmulDS-Shim, un programa pequeño de Sanrax que le pasa el juego y lo adapta al DSpico. Por eso
son cinco archivos, y los cinco van juntos en `_pico/emulators`:

- Del paquete «SNEmulDS 0.6d & 0.6a package», el enlace del primer paso de la pestaña «SNES» de Sanrax.
  Es un zip con `SNEmulDS.nds`, `SNEmulDS.srl` y `SNEmulDS_0.6a.nds`. Usa estos y no otras versiones de
  SNEmulDS: el shim está hecho para estos tres archivos exactos.
- De los enlaces de los pasos 4 y 5 de esa pestaña: `snemulds-shim.nds` y `snemulds-shim.ini`.

Al abrir un juego sale el menú del shim. La primera opción suele ir bien. Desde ahí también puedes abrir el
juego en modo DS en una DSi o una 3DS, usar la versión antigua, la 0.6a, o hacer que la próxima vez
arranque directamente, sin el menú.

SNEmulDS no puede con todos los juegos. En la pestaña «SNES», Sanrax enlaza una lista, en inglés, que dice
cuáles van y con qué ajustes. En una DSi o una 3DS la consola tiene más memoria, y Coto dice que algunos
juegos solo van ahí.

## NES

Usa `nesDS.nds`, el que enlaza Sanrax. nesDS guarda la partida en la carpeta del juego, pero de fábrica no
la escribe por su cuenta mientras juegas, y a un usuario con una DS Lite no se le guardaba ninguna. Antes
de apagar, guárdala a mano: toca la pantalla de abajo para que salga el menú de nesDS y elige «File» >
«Save SRAM». En ese mismo menú, «Stat: Manual» quiere decir que no guarda solo.

El menú también tiene estados de guardado («Save State» y «Load State»), pero con algunos juegos, como
Metroid, cargar uno rompe los gráficos.

En una DSi, nesDS necesita una tarjeta SD en la ranura de la propia consola: mira
[En una DS, una DSi o una 3DS](#en-una-ds-una-dsi-o-una-3ds).

## Mega Drive y Genesis

El bloque asocia a jEnesisDSPlus los juegos `.gen` y `.smd`. Si los tuyos acaban en `.md`, cámbiales la
extensión a `.gen`, como pide la guía de Sanrax.

La guía de Sanrax tiene otro emulador de Mega Drive, PicoDriveTWL. Según Sanrax es más fiel, pero algo más
lento. Además, no tiene sonido, ni en la versión que enlaza Sanrax ni en la más nueva. Si aun así lo
prefieres, cambia `jEnesisDSPlus.nds` por `PicoDriveTWL.nds` en las líneas de `gen` y `smd` del bloque.

## Neo Geo

NeoDS se instala distinto, como dice la pestaña «NeoGeo» de Sanrax:

1. Crea una carpeta `Emulators` en la raíz de la microSD, aparte de `_pico/emulators`, y copia en ella
   `NeoDS.nds`.
2. Crea la carpeta `data/NeoDS` y pon en ella el archivo `_NeoDS.ini` que enlaza Sanrax.
3. Los juegos hay que convertirlos antes a `.neo` en la computadora con NeoDsConvert, un programa de
   Windows que necesita el BIOS de la Neo Geo, `neogeo.zip`. En la microSD no va ningún BIOS. Los pasos
   están, en inglés, en la página que enlaza Sanrax en el paso 7 de su pestaña. Copia los `.neo` en
   `ROMs/NeoGeo`.
4. Para jugar, abre `NeoDS.nds` desde Pico Launcher y elige el juego en el menú de NeoDS.

## Las demás consolas

S8DS, NGPDS y NitroGrafx son de FluBBa, y su menú sale con L+R o tocando la pantalla.

- S8DS, el de Master System y Game Gear, guarda ajustes y partidas en `data/S8DS`, que tienes que crear.
  Con `.sg` y `.sc` también abre juegos de SG-1000 y SC-3000. El BIOS es opcional: va en `ROMs/BIOS` y se
  activa en su menú, en «Options» > «Machine» > «Bios Settings».
- NGPDS, el de Neo Geo Pocket, necesita la carpeta `data/NGPDS` con el `settings.cfg` que enlaza Sanrax.
  Sin el BIOS se puede jugar, pero no guardar dentro del juego. Va en `ROMs/BIOS` con estos nombres:
  `ngp-color-bios.ngp`, el de la Pocket Color, y `ngp-bnw-bios.ngp`, el de la Pocket en blanco y negro.
  En una DS o una DS Lite, los juegos de más de 2 MB necesitan un cartucho de memoria en la ranura de GBA.
- NitroGrafx, el de PC Engine, guarda ajustes y partidas en `data/NitroGrafx`, que tienes que crear. Los
  juegos en CD necesitan un BIOS de CD-ROM en la carpeta de los juegos, que se elige en su menú, en
  «Options» > «Machine» > «Bios Settings» > «Select Bios». Un `.iso` suelto solo vale para juegos con una
  sola pista de datos; si no, el disco va como `.bin` con su `.cue`. Si al abrir un juego dice que no
  encuentra `settings.cfg`, elige en su menú «File» > «Save Settings»: a un usuario se le arregló así. No
  emula la SuperGrafx.
- StellaDS, el de Atari 2600, abre los juegos `.a26`. Si los tuyos acaban en `.bin`, cámbiales la
  extensión a `.a26`.
- A5200DS, el de Atari 5200, trae un BIOS propio que no va con todos los juegos. El original, `5200.rom`,
  va en `ROMs/BIOS`. Los juegos `.bin` se cambian a `.a52`.
- A7800DS, el de Atari 7800, va mejor con las versiones NTSC de los juegos, según su autor. Los `.bin` se
  cambian a `.a78`. El BIOS original, `7800.rom`, es opcional, y con `highscore.rom` guarda los récords:
  los dos van en `ROMs/BIOS`.
- A8DS, el de Atari 800 y 400, trae su propio BIOS y acepta los originales en `ROMs/BIOS`, con los nombres
  que da Sanrax.
- ColecoDS necesita el BIOS de ColecoVision, `coleco.rom`, en `ROMs/BIOS`. También abre juegos de MSX,
  Sord M5, Memotech MTX y otros sistemas parecidos, con las demás extensiones del bloque: `.cv`, `.cas`,
  `.com`, `.ddp`, `.dsk`, `.mtx`, `.msx`, `.m5`, `.pen`, `.pv` y `.pv1`.
- NINTV-DS, el de Intellivision, necesita dos archivos del BIOS, `grom.bin` y `exec.bin`, en `ROMs/BIOS`.

## En una DS, una DSi o una 3DS

En una DS o una DS Lite, todos los emuladores funcionan en [modo DS](../glosario.md#modo-ds). En una DSi
o una 3DS, Pico Loader abre casi todos en [modo DSi](../glosario.md#modo-dsi), con el procesador al doble
de velocidad y más memoria, y ahí van mejor. wavemotion-dave, el autor de los emuladores de Atari,
ColecoVision e Intellivision, avisa de que en una DS Lite algunos juegos van más lentos. jEnesisDSPlus,
GameYob y NeoDS van en modo DS en cualquier consola.

En modo DSi, nesDS y otros emuladores se quedan en blanco o cuelgan la consola si la DSi no tiene una
tarjeta SD en su propia ranura. Lo explica
[Un emulador se queda en blanco o colgado en una DSi](problemas.md#un-emulador-se-queda-en-blanco-o-colgado-en-una-dsi).
En una 3DS pasa lo mismo, pero casi nunca se nota, porque la 3DS suele llevar su tarjeta puesta.

## Si no funciona

- El juego no sale en la lista. Si está dentro de un `.zip` o un `.7z`, descomprímelo antes. Si no es eso,
  su extensión no tiene asociación: mira que acabe como dice la tabla y que `settings.json` siga teniendo
  el bloque.
- Sale «Failed to open the rom file.» con la ruta de un emulador debajo: el emulador no está en esa ruta.
  Pon el `.nds` en `_pico/emulators`, con el nombre exacto del bloque.
- El juego sale en la lista, pero al abrirlo la pantalla se queda en blanco o la consola se cuelga: el
  fallo es del emulador en esa consola. En una DSi, mira antes lo de la tarjeta SD en
  [En una DS, una DSi o una 3DS](#en-una-ds-una-dsi-o-una-3ds).

## Volver al menú

Si el emulador tiene en su menú una opción para salir, como «File» > «Quit Emulator» en S8DS, NGPDS y
NitroGrafx, al usarla vuelves a Pico Launcher. Si no la tiene, guarda la partida y apaga la consola.

## Fuentes

Esta página se basa en la
[guía de emuladores de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/emulators-pico/),
en la documentación de [Pico Launcher](https://github.com/LNH-team/pico-launcher) sobre asociaciones y
en la página de cada emulador: [GameYob](https://github.com/Stewmath/GameYob),
[SNEmulDS](https://github.com/cotodevel/snemulds),
[SNEmulDS-Shim](https://github.com/Sanrax/snemulds-shim), [nesDS](https://github.com/DS-Homebrew/NesDS),
[jEnesisDSPlus](https://github.com/DS-Homebrew/jEnesisDSPlus),
[PicoDriveTWL](https://github.com/DS-Homebrew/PicoDriveTWL), [S8DS](https://github.com/FluBBaOfWard/S8DS),
[NGPDS](https://github.com/FluBBaOfWard/NGPDS), [NitroGrafx](https://github.com/FluBBaOfWard/NitroGrafx),
[StellaDS](https://github.com/wavemotion-dave/StellaDS), [A5200DS](https://github.com/wavemotion-dave/A5200DS),
[A7800DS](https://github.com/wavemotion-dave/A7800DS), [A8DS](https://github.com/wavemotion-dave/A8DS),
[ColecoDS](https://github.com/wavemotion-dave/ColecoDS) y
[NINTV-DS](https://github.com/wavemotion-dave/NINTV-DS). También usa casos de usuarios en r/flashcarts,
r/DsPico y GBAtemp. Casi todas están en inglés.
