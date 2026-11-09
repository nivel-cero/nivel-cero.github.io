---
title: "Glosario"
BookIcon: libro
weight: 20
reviewed: 2026-11-08
---

Las palabras de esta guía que quizá no conozcas, en orden alfabético. Debajo de cada una va un enlace a la
página que cuenta más. Para ir a una, elígela en la lista de la derecha (en el celular, en el botón de
arriba a la derecha) o búscala con Ctrl+F (Comando + F en Mac, o «Buscar en la página» en el navegador
del celular). Como en el resto de la guía, «DSi» incluye la DSi XL, y «3DS» incluye la 2DS y los modelos
XL y New.

## Archivo oculto

Archivo o carpeta que la computadora no muestra, salvo que actives la opción de ver los elementos ocultos.
Pico Launcher tampoco los muestra: si ocultas la carpeta `_pico` y el archivo `_picoboot.nds`, dejan de
salir en el menú, y el cartucho los sigue encontrando.

[Primeros pasos > Ocultar carpetas y archivos del menú](dspico/primeros-pasos.md#ocultar-carpetas-y-archivos-del-menú)

## Archivo partido en trozos

La microSD guarda cada archivo en trozos. Si haces varias copias al mismo tiempo, por ejemplo arrastrando
un juego mientras otro se sigue copiando o sacándolos directamente de un `.zip`, los trozos de cada juego
pueden quedar mezclados con los de los demás. Si un juego queda muy partido, Pico Loader no lo lee bien y
no avisa: el juego se queda en blanco o en negro, o da otro error.

[Problemas > Un juego partido en muchos trozos](dspico/problemas.md#un-juego-partido-en-muchos-trozos)

## Archivos `._` del Mac {#archivos-del-mac}

Archivos ocultos que crea el Mac al copiar algo a una tarjeta en FAT32: uno por cada archivo, con el mismo
nombre y `._` delante. Pueden dejar la pantalla en negro al abrir el DSpico en una DSi o una 3DS, así que
hay que borrarlos antes de expulsar la tarjeta.

[Problemas > Pantalla negra en una DSi o una 3DS, con un Mac](dspico/problemas.md#pantalla-negra-en-una-dsi-o-una-3ds-con-un-mac)

## BIOS

Programa básico que va grabado de fábrica en una consola o una computadora: la prepara al encenderla y trae
funciones que usan los demás programas. La DS tiene uno en cada uno de sus dos procesadores, y Pico Loader
necesita una copia del de ARM7, el archivo `biosnds7.rom`, para abrir [DSiWare](#dsiware) y las copias de
juegos con la [zona segura](#zona-segura) cifrada.

[Problemas > Un juego cifrado sin el BIOS](dspico/problemas.md#un-juego-cifrado-sin-el-bios)

## Cartucho flash

Cartucho con una ranura para una tarjeta de memoria, como una microSD: la consola abre los juegos y
programas que copies en esa tarjeta. En inglés se llama *flashcart*, y el DSpico y las R4 lo son.

[DSpico](dspico/_index.md)

## CFW

Siglas de *custom firmware*, firmware personalizado: un sistema modificado de la consola, como
[Luma3DS](#luma3ds) en la 3DS o [HiyaCFW](#hiyacfw) en la DSi. Aunque lleve la palabra firmware, no tiene
que ver con el [firmware](#firmware) del DSpico, que va grabado en el cartucho.

[El firmware > Qué cuenta como modificada](dspico/firmware.md#qué-cuenta-como-modificada)

## Consola modificada

Para el DSpico, una DSi con [Unlaunch](#unlaunch) o una 3DS con un sistema modificado ([CFW](#cfw)), como
Luma3DS; una DSi que solo abre TWiLight Menu++ desde una aplicación de la consola, sin Unlaunch, no cuenta.
De eso depende qué variante del firmware necesita el cartucho.

[El firmware > Qué cuenta como modificada](dspico/firmware.md#qué-cuenta-como-modificada)

## Descomprimir

Sacar lo que hay dentro de un archivo comprimido, como un `.zip` o un `.7z`. Pico Launcher y Pico Loader se
descargan en `.zip`, y el menú del DSpico no muestra los juegos comprimidos: descomprime unos y otros en la
computadora antes de copiarlos a la microSD.

[Primeros pasos > Instalar Pico Launcher y Pico Loader](dspico/primeros-pasos.md#instalar-pico-launcher-y-pico-loader)

## DSiWare

Juegos y programas que se descargaban de la tienda de la DSi. El DSpico los abre en una DSi o una 3DS, en
[modo DSi](#modo-dsi), pero hacen falta el archivo `biosnds7.rom`, una copia del [BIOS](#bios) de una DS, y
archivos de la memoria interna de una DSi o una 3DS, que esta guía todavía no explica.

[Antes de comprar > Qué hace y qué no hace](dspico/antes-de-comprar.md#qué-hace-y-qué-no-hace)

## DSpico

[Cartucho flash](#cartucho-flash) para la DS que también funciona en la DSi y la 3DS. Lo diseña el
[LNH Team](#lnh-team), que publica gratis el diseño y el código, y lo fabrican y venden tiendas sin
relación con él.

[DSpico](dspico/_index.md)

## Emulador

Programa que hace que una consola o una computadora funcione como otra, para abrir sus juegos. Por ejemplo,
nesDS abre juegos de NES en la DS.

[Problemas > Un emulador se queda en blanco o colgado en una DSi](dspico/problemas.md#un-emulador-se-queda-en-blanco-o-colgado-en-una-dsi)

## exFAT

Una forma de organizar los archivos en una tarjeta, como [FAT32](#fat32). Las microSD de 64 GB o más
vienen de fábrica en exFAT, y ningún programa del DSpico lo lee: hay que [formatearlas](#formatear) en
FAT32.

[Primeros pasos > La microSD](dspico/primeros-pasos.md#la-microsd)

## Extensión

Lo que va al final del nombre de un archivo, después del punto, y dice de qué tipo es: `.nds` en un juego de
DS, `.sav` en una partida. Windows a veces la esconde, y si al cambiarle el nombre al archivo la escribes
otra vez, queda con dos, como `_picoboot.nds.nds`.

[Primeros pasos > Instalar Pico Launcher y Pico Loader](dspico/primeros-pasos.md#instalar-pico-launcher-y-pico-loader)

## FAT32

Una forma de organizar los archivos en una tarjeta o un disco, lo que se llama sistema de archivos. El
DSpico solo funciona con la microSD en FAT32, y en la computadora puedes ver en qué está la tuya.

[Primeros pasos > La microSD](dspico/primeros-pasos.md#la-microsd)

## Firmware

Programa grabado en la memoria de un aparato, como un cartucho o una consola. En las páginas del DSpico es
casi siempre el del cartucho; no hay que confundirlo con Pico Launcher ni con Pico Loader, que son archivos
de la microSD.

[El firmware](dspico/firmware.md)

## Flashear

Grabar un [firmware](#firmware) nuevo en un aparato. En el DSpico se hace desde la computadora, con un cable
USB, y si el cartucho ya te funciona en tus consolas, no hace falta.

[El firmware > ¿Necesito flashearlo?](dspico/firmware.md#necesito-flashearlo)

## Formatear

Preparar una tarjeta o un disco con un sistema de archivos, como [FAT32](#fat32). Borra todo lo que tenga:
copia antes a la computadora lo que quieras conservar.

[Primeros pasos > La microSD](dspico/primeros-pasos.md#la-microsd)

## GBARunner

GBARunner2 y su sucesor, GBARunner3, son programas que abren juegos de GBA en una DS, una DSi o una 3DS.
Esta guía los llama [emuladores](#emulador), aunque el código del juego funciona directamente en el
procesador de la consola y el programa solo imita el resto de la GBA: por eso su autor principal, Gericom,
describe GBARunner2 como *hypervisor*.

[Problemas > GBA](dspico/problemas.md#gba)

## HiyaCFW

Sistema modificado ([CFW](#cfw)) para la DSi: hace que la consola arranque desde la tarjeta SD de su propia
ranura, y no desde su memoria interna. Necesita [Unlaunch](#unlaunch), así que una DSi con HiyaCFW cuenta
como [modificada](#consola-modificada).

[Problemas > Se queda en WRFU Tester](dspico/problemas.md#se-queda-en-wrfu-tester)

## Homebrew

Programas caseros: juegos y aplicaciones que hacen aficionados para una consola, y que no publica su
fabricante. Con el DSpico se copian en la microSD y se abren igual que los juegos comerciales.

[Antes de comprar > Qué hace y qué no hace](dspico/antes-de-comprar.md#qué-hace-y-qué-no-hace)

## Hybrid

Una de las dos variantes del [firmware](#firmware) del DSpico, junto a [WRFUxxed](#wrfuxxed); en el menú de
una DSi o una 3DS sale con el icono de una frambuesa. Funciona en una DS, una DS Lite y en las DSi y 3DS
[modificadas](#consola-modificada), pero en una DSi o una 3DS sin modificar sale «Se ha producido un
error».

[El firmware > Las dos variantes](dspico/firmware.md#las-dos-variantes)

## Issue

Aviso de un fallo en un proyecto de GitHub, la web donde los autores de muchos programas caseros, como Pico
Loader, publican su código. Para abrir una hace falta una cuenta de GitHub, y las de Pico Loader se
escriben en inglés.

[Problemas > Si nada de esto funciona](dspico/problemas.md#si-nada-de-esto-funciona)

## LNH Team

El grupo que diseña el DSpico y hace Pico Launcher y Pico Loader. Publica gratis el diseño y el código, y no
vende el cartucho ni recomienda tiendas.

[Antes de comprar > ¿Original o falso?](dspico/antes-de-comprar.md#original-o-falso)

## Luma3DS

Un sistema modificado ([CFW](#cfw)) para la 3DS; una 3DS con Luma3DS cuenta como
[modificada](#consola-modificada). Para saberlo, con la consola apagada, mantén pulsado SELECT y
enciéndela: si sale un menú de configuración, lo tiene. No cambies nada en él: apaga la consola.

[El firmware > Qué cuenta como modificada](dspico/firmware.md#qué-cuenta-como-modificada)

## microSD

La tarjeta de memoria más pequeña del formato SD. La del DSpico va dentro del cartucho y guarda los juegos,
las partidas y los archivos de Pico Launcher y Pico Loader; tiene que estar en [FAT32](#fat32), y conviene
que sea de marca y original.

[Primeros pasos > La microSD](dspico/primeros-pasos.md#la-microsd)

## Modo DS

La forma en que una DSi o una 3DS abre un juego como si fuera una DS, sin lo que la DSi tiene de más, que es
el [modo DSi](#modo-dsi). Los cartuchos flash que se venden hoy, salvo el DSpico, arrancan así.

[Antes de comprar > ¿DSpico o R4?](dspico/antes-de-comprar.md#dspico-o-r4)

## Modo DSi

La forma en que una DSi o una 3DS abre un juego con lo que la DSi tiene de más que la DS, como la cámara.
Es lo que permite abrir [DSiWare](#dsiware), y en una DS o una DS Lite no existe: ahí todo va en
[modo DS](#modo-ds).

[Antes de comprar > Qué hace y qué no hace](dspico/antes-de-comprar.md#qué-hace-y-qué-no-hace)

## `.nds` {#nds}

[Extensión](#extensión) de los juegos y los programas de DS: `Juego.nds` es un juego, y `_picoboot.nds` es
Pico Launcher. El menú del DSpico también muestra los `.srl` y los `.dsi`.

[Primeros pasos > Los juegos](dspico/primeros-pasos.md#los-juegos)

## nds-bootstrap

Programa que arranca juegos de DS, como hace Pico Loader. Lo usa [TWiLight Menu++](#twilight-menu) para
abrir juegos desde la tarjeta SD de la consola, y con el DSpico algunos usuarios abren con él varios ROM
hacks de Pokémon que Pico Loader deja en blanco.

[Problemas > Juegos que no funcionan](dspico/problemas.md#juegos-que-no-funcionan)

## Parche

Cambio que se hace en un programa. Pico Loader cambia algunas partes de cada juego comercial para que
funcione desde la microSD, y si no puede, sale un error.

[Problemas > «Failed to apply arm9 patches.» y «Failed to apply arm7 patches.»](dspico/problemas.md#failed-to-apply-arm9-patches-y-failed-to-apply-arm7-patches)

## Pico Launcher

El menú del DSpico: la pantalla donde eliges el juego. Se instala y se actualiza copiando sus archivos en la
microSD, y no muestra su versión en ninguna parte.

[Primeros pasos > Instalar Pico Launcher y Pico Loader](dspico/primeros-pasos.md#instalar-pico-launcher-y-pico-loader)

## Pico Loader

El programa que arranca el juego que eliges en [Pico Launcher](#pico-launcher). Se instala copiando sus
archivos en la carpeta `_pico` de la microSD. Si detecta un fallo al abrir un juego, muestra un mensaje en
inglés con letras blancas sobre fondo negro; si no lo detecta, la pantalla se queda en blanco sin ningún
mensaje.

[Problemas > Mensajes al abrir un juego](dspico/problemas.md#mensajes-al-abrir-un-juego)

## R4

Nombre de un [cartucho flash](#cartucho-flash) para la DS que tiene muchísimos clones, y lo que sirve para
uno no siempre sirve para otro. Algunos traen una «bomba de tiempo» que no deja entrar al menú pasada una
fecha.

[Antes de comprar > ¿DSpico o R4?](dspico/antes-de-comprar.md#dspico-o-r4)

## Raíz

Lo que ves al abrir la microSD en la computadora, fuera de cualquier carpeta. Ahí van la carpeta `_pico` y
el archivo `_picoboot.nds`, y en los mensajes de Pico Loader, al principio de la [ruta](#ruta) de un juego,
se escribe `fat:/`.

[Primeros pasos > Instalar Pico Launcher y Pico Loader](dspico/primeros-pasos.md#instalar-pico-launcher-y-pico-loader)

## ROM

Siglas en inglés de *read-only memory*, memoria de solo lectura: un chip que se graba al fabricarlo y
después ya no se puede cambiar. Los juegos iban grabados en uno dentro del cartucho, y por eso se llama ROM
al archivo con la copia de un juego, como en el mensaje «Failed to open the rom file.» de Pico Loader. El
`biosnds7.rom` del [BIOS](#bios) también es la copia de un chip así, pero no es un juego.

[Problemas > Mensajes al abrir un juego](dspico/problemas.md#mensajes-al-abrir-un-juego)

## ROM hack

Versión de un juego modificada por aficionados, con otros gráficos, textos, niveles o forma de jugar; las
traducciones de aficionados también lo son. Algunos fallan con Pico Loader aunque el juego original
funcione.

[Problemas > Juegos que no funcionan](dspico/problemas.md#juegos-que-no-funcionan)

## Ruta

El camino hasta un archivo: las carpetas donde está, de fuera hacia dentro, y al final su nombre, separados
por una barra (`/`, o `\` en Windows). En los mensajes de Pico Loader, la ruta de un juego empieza por
`fat:/`, que es la [raíz](#raíz) de la microSD: `fat:/Juegos/Juego.nds` es el archivo `Juego.nds` dentro de
la carpeta `Juegos`.

[Problemas > «Failed to open the rom file.»](dspico/problemas.md#failed-to-open-the-rom-file)

## `.sav` {#sav}

[Extensión](#extensión) del archivo de la partida de un juego de DS, que va junto al juego y con su mismo
nombre: la de `Juego.nds` es `Juego.sav`. Si mueves el juego o le cambias el nombre, haz lo mismo con su
`.sav`.

[Problemas > Partidas](dspico/problemas.md#partidas)

## TWiLight Menu++

Menú casero que se instala en la DSi o la 3DS y, con [nds-bootstrap](#nds-bootstrap), abre juegos de DS
desde la tarjeta SD de la consola, sin cartucho. También funciona en el DSpico.

[Antes de comprar > ¿DSpico o TWiLight Menu++?](dspico/antes-de-comprar.md#dspico-o-twilight-menu)

## Unlaunch

Programa que se instala en la DSi y la modifica; una DSi con Unlaunch cuenta como
[modificada](#consola-modificada). Para saberlo, saca el cartucho y, con la DSi apagada, pulsa POWER y en
seguida mantén pulsados A y B: si en la pantalla de arriba sale «Nocash Unlaunch.dsi», lo tiene. No cambies
nada en ese menú: apaga la consola.

[El firmware > Qué cuenta como modificada](dspico/firmware.md#qué-cuenta-como-modificada)

## WRFUxxed

Una de las dos variantes del [firmware](#firmware) del DSpico, junto a [Hybrid](#hybrid): funciona en
cualquier DS, DSi o 3DS, también sin [modificar](#consola-modificada), y en el menú de la 3DS sale como
«Nintendo DS Demonstration». Lleva dentro WRFU Tester, un programa de pruebas de Nintendo, y por eso no se
puede compartir legalmente ya hecho: hay que prepararlo con tu propia copia de ese programa.

[El firmware > Las dos variantes](dspico/firmware.md#las-dos-variantes)

## Zona segura

El principio de un juego de DS, que en algunas copias está cifrado. Para abrir esas copias, Pico Loader
necesita el archivo `biosnds7.rom`, una copia del [BIOS](#bios) de la DS; sin él, el juego se queda en
blanco sin ningún mensaje.

[Problemas > Un juego cifrado sin el BIOS](dspico/problemas.md#un-juego-cifrado-sin-el-bios)

## Fuentes

Las definiciones salen de las demás páginas de esta guía, que llevan sus propias fuentes. Para las palabras
que ninguna otra página explica, esta página usa también Wikipedia
([memoria de solo lectura](https://es.wikipedia.org/wiki/Memoria_de_solo_lectura),
[ROM hacking](https://en.wikipedia.org/wiki/ROM_hacking), [BIOS](https://es.wikipedia.org/wiki/BIOS),
[emulador](https://es.wikipedia.org/wiki/Emulador), [hipervisor](https://en.wikipedia.org/wiki/Hypervisor),
[tarjeta SD](https://en.wikipedia.org/wiki/SD_card) y [ruta](https://es.wikipedia.org/wiki/Ruta_(inform%C3%A1tica))),
la [SD Association](https://www.sdcard.org/developers/sd-standard-overview/capacity-sd-sdhc-sdxc-sduc/)
para la microSD, [GBATEK](https://problemkaputt.de/gbatek-ds-memory-maps.htm) para el BIOS de la DS, la
[wiki de DS-Homebrew](https://wiki.ds-homebrew.com/es-ES/hiyacfw/) y
[dsi.cfw.guide](https://dsi.cfw.guide/installing-unlaunch-and-hiyacfw.html) para HiyaCFW, y el código de
[Pico Loader](https://github.com/LNH-team/pico-loader), del
[bootloader del DSpico](https://github.com/LNH-team/dspico-bootloader), de
[GBARunner2](https://github.com/Gericom/GBARunner2), de [GBARunner3](https://github.com/Gericom/GBARunner3)
y de [nesDS](https://github.com/DS-Homebrew/NesDS). Casi todas están en inglés.
