---
title: "El firmware"
weight: 30
versions: ["Firmware oficial 1.0.1"]
reviewed: 2026-10-28
---

El firmware es el programa que va grabado en la memoria del propio cartucho. No hay que confundirlo con
Pico Launcher (el menú del DSpico) ni con Pico Loader (el que arranca los juegos): esos dos son archivos
de la microSD.

> [!IMPORTANT]
> Si tu DSpico ya funciona bien en tus consolas, no hace falta tocar el firmware. Para tener una versión
> nueva de Pico Launcher o de Pico Loader basta con cambiar sus archivos de la microSD por los nuevos. De
> Pico Loader, usa siempre el paquete del DSpico (`Pico_Loader_DSPICO.zip`), aunque tu cartucho se
> parezca a otro: sus autores avisan de que el de otro cartucho puede dañarlo.

## ¿Necesito flashearlo?

Flashear es grabar un firmware nuevo en el cartucho. Las guías lo piden en estos casos:

- **La consola no ve el cartucho, o se queda colgada al encenderla con él puesto.** Antes de pensar en
  el firmware, comprueba lo fácil. Dentro del cartucho tiene que haber una microSD formateada en FAT32:
  sin ella no funciona. Si no sabes cómo comprobarlo, lo explica el
  [tutorial de formateo de Sanrax](https://sanrax.github.io/flashcart-guides/tutorials/formatting/) (en
  inglés); formatear borra todo lo que tiene la tarjeta. La ranura de la consola tiene que estar limpia:
  la guía de Sanrax aconseja soplarla con aire comprimido. Si aun así no aparece, puede que te llegara
  sin firmware: no todos lo traen.
- **En una DSi, una 3DS o una 2DS, el cartucho aparece en el menú, pero al abrirlo sale un error que te
  pide apagar la consola.** Puede pasar aunque en una DS o una DS Lite funcione bien. Mira
  [Si tu DSi o tu 3DS dice «Se ha producido un error»](#si-tu-dsi-o-tu-3ds-dice-se-ha-producido-un-error)
  antes de hacer nada.
- **Los juegos van a saltos o se congelan al azar, y tu microSD es de marca y original.** Si no estás
  seguro de que lo sea, prueba antes con otra que sí lo sea. Si solo falla un juego concreto, prueba con
  la última versión de Pico Loader, que trae arreglos para juegos concretos. Si pasa igual, puede que tu
  cartucho tenga un firmware antiguo, de antes de que se arreglaran los fallos con algunas tarjetas.

La guía de Sanrax recomienda volver a grabar el firmware para tener su última versión, pero también deja
saltarse ese paso si el que trae te sirve.

Los cartuchos que se venden como «DSpico Lite», o con una carcasa parecida a la de otro cartucho, el
Ace3DS+, no suelen tener puerto USB. Mira si el tuyo lo tiene: sin él no se puede cambiar el firmware.

## Las dos variantes

Hay dos variantes del firmware. Las dos funcionan en una DS, una DS Lite y en las consolas modificadas.
La diferencia está en las DSi y 3DS sin modificar
(más abajo verás [qué cuenta como modificada](#qué-cuenta-como-modificada)):

| Variante | DS y DS Lite | DSi y 3DS sin modificar | DSi y 3DS modificadas |
|---|---|---|---|
| **WRFUxxed** | Sí | Sí | Sí |
| **Hybrid** | Sí | **No** | Sí |

En esta página, «DSi» incluye la DSi XL, y «3DS» incluye la 2DS y los modelos XL y New.

- Si tu cartucho ya funciona en todas las consolas donde lo vas a usar, no lo cambies.
- Si vas a usarlo en alguna DSi o 3DS sin modificar, aunque sea la de otra persona, necesitas WRFUxxed.
- Si todas esas consolas están modificadas, sirven las dos. La guía de Sanrax sugiere Hybrid, porque con
  WRFUxxed la DSi abre el cartucho sola al encenderse, sin pasar por su menú.

### Qué cuenta como modificada

- **Una DSi con Unlaunch**, un programa que se instala en la consola y la modifica. Para saberlo, saca el
  cartucho y, con la DSi apagada, pulsa POWER y en seguida mantén pulsados A y B. Si sale un menú con
  «Nocash Unlaunch.dsi» en la pantalla de arriba, lo tiene. Si arranca el menú de siempre, no lo tiene.
- **Una 3DS con el sistema modificado**: lo que se llama custom firmware o CFW, como Luma3DS. Ojo: aquí
  se habla del sistema de la consola, no del firmware del cartucho. Para saberlo, con la consola apagada,
  mantén pulsado SELECT y enciéndela sin soltarlo. Si sale un menú de configuración, lo tiene. Si arranca
  el menú HOME de siempre, no lo tiene.

Si sale uno de esos menús, no cambies nada en él: apaga la consola.

Una DSi que solo abre TWiLight Menu++ desde una aplicación de la consola (la Cámara, el Navegador o
Flipnote Studio) no cuenta como modificada: sin Unlaunch, para el cartucho es una DSi normal. Y si
compraste la consola de segunda mano, puede que ya venga modificada sin que lo sepas: haz la prueba igual.

> [!TIP]
> En una DSi con Unlaunch y Hybrid, abre el cartucho desde el menú normal de la DSi. Algunos usuarios
> cuentan que, abierto desde TWiLight Menu++ o con la opción de cartucho de Unlaunch, se quedaba en una
> pantalla blanca o negra, o salía «Failed to mount SD card». Si tu DSi no muestra ese menú al
> encenderse, en las opciones de Unlaunch se le puede asignar un botón: se llama «Launcher».

## Qué variante lleva tu cartucho

Para saberlo hace falta una DSi o una 3DS:

1. Pon dentro del cartucho una microSD en FAT32. Si ya usas una con el cartucho, vale esa: no la
   formatees para esto.
2. Con la consola apagada, mete el cartucho y enciéndela.
3. Mira qué pasa:
   - Si en el menú aparece con el icono de una frambuesa y el nombre «DSpico» y «LNH team», lleva
     **Hybrid**. Si al abrirlo funciona, déjalo así. Si sale un error, mira
     [Si tu DSi o tu 3DS dice «Se ha producido un error»](#si-tu-dsi-o-tu-3ds-dice-se-ha-producido-un-error).
   - Si aparece como «Nintendo DS Demonstration», con un icono gris, lleva **WRFUxxed**. En una 3DS,
     WRFUxxed siempre sale así. Es normal: no hay que cambiar nada.
   - Si es una DSi sin Unlaunch y el cartucho arranca solo, saltándose el menú, lleva **WRFUxxed**. Por
     un momento verás «\*\*\* WRFU Tester v0.60 \*\*\*» en la pantalla de abajo. Después se abre Pico
     Launcher si la microSD ya tiene sus archivos. Si sale una pantalla roja, faltan los archivos de
     Pico Loader en la carpeta `_pico`. Si sale azul, no se puede leer la microSD: prueba con otra, de
     marca y original. En los dos casos revisa la microSD antes de pensar en el firmware.
   - Si no aparece de ninguna forma, mira el primer caso de [¿Necesito flashearlo?](#necesito-flashearlo).

En una DS o una DS Lite no se puede saber: las dos variantes se ven igual. Tampoco importa, porque ahí
funcionan las dos.

## Si tu DSi o tu 3DS dice «Se ha producido un error»

El cartucho aparece en el menú de la consola, pero al abrirlo sale un mensaje que te pide mantener
pulsado POWER para apagarla, con letras blancas sobre fondo negro. El texto exacto cambia según la
consola y el idioma. Por ejemplo:

- En una 3DS en español: «Se ha producido un error. Mantén oprimido el botón POWER para apagar la
  consola. Consulta el manual de instrucciones de la consola para obtener más información.»
- En una DSi en español puede decir: «Se ha producido un error. Mantén oprimido el Botón POWER para
  apagar la consola. Consulta el manual de operaciones de la consola para obtener más información.»
- En una DSi en inglés: «An error has occurred. Press and hold the Power Button to turn the system off…»

Si en el menú salía con el icono de la frambuesa, el cartucho lleva Hybrid, y para el cartucho tu
consola cuenta como no modificada. Si salía con otro icono, o el mensaje sale también al abrir otras
cosas del menú, no es este caso: no flashees ni modifiques la consola, y pide ayuda en [r/flashcarts](https://www.reddit.com/r/flashcarts/)
contando qué ves. Es un foro de Reddit en inglés, pero también hay quien pregunta en español. Si
el mensaje es otro, como «Failed to mount SD card» o una pantalla roja o azul, revisa primero la microSD
y sus archivos.

No hemos encontrado ningún caso de una consola dañada por este error. En los casos en que sabemos cómo
acabó, el cartucho funcionó en esa misma consola después de flashearlo con WRFUxxed.

Tienes tres opciones:

1. **Dejarlo como está.** Con Hybrid, el cartucho sigue funcionando en una DS y una DS Lite.
2. **Flashear el cartucho con WRFUxxed.** Este firmware lleva dentro WRFU Tester v0.60, un programa de
   pruebas de Nintendo. Por eso el firmware completo no se puede compartir legalmente ya hecho: hay que
   prepararlo con tu propia copia de ese programa. Si no la tienes, esta opción no es para ti. Si la
   tienes, lee primero [Cómo se flashea](#cómo-se-flashea); la guía de Sanrax explica después cómo se
   prepara.
3. **Modificar la consola.** No hace falta para usar el cartucho, y no te lo recomendamos solo para
   esto, porque tiene sus propios riesgos. En la DSi tiene que ser con Unlaunch, e instalarlo escribe en
   la memoria interna de la consola: hay una pequeña posibilidad de dejarla inservible. Si aun así
   quieres hacerlo, sigue las guías de referencia: [dsi.cfw.guide](https://dsi.cfw.guide/) para la DSi y
   [3ds.hacks.guide](https://3ds.hacks.guide/) para la 3DS. En la de la DSi, la opción pensada para este
   error se llama «Unlaunch Standalone».

## Cómo se flashea

> [!CAUTION] Hazlo solo si lo necesitas
> Si copias un archivo equivocado o desconectas el cable a mitad, el cartucho puede dejar de funcionar
> hasta que lo vuelvas a flashear bien, y para eso puede hacer falta un botón al que no todas las
> carcasas dejan llegar. Antes de empezar, lee también [Si algo sale mal](#si-algo-sale-mal). Si no
> sabes seguro qué variante necesitas, no sigas.

Necesitas:

- Un cartucho con puerto USB.
- Un cable que encaje en ese puerto (micro USB o USB-C, según el modelo) y que transmita datos: algunos
  cables solo sirven para cargar.
- Una computadora (un PC o un ordenador).
- El archivo `.uf2` de la variante que necesitas. El LNH Team, que diseña el DSpico, no publica el
  firmware listo para grabar: solo publica su código. La
  [guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/) (en
  inglés, no es del LNH Team) explica los pasos de cada variante. Para WRFUxxed hace falta además tu
  propia copia de WRFU Tester v0.60. Los archivos de esa guía llevan la variante en el nombre («Hybrid»
  o «wrfuxxed»): no uses uno que no lo diga, ni uno que te pase otra persona. Allí verás también una
  opción llamada «Devkit (Panda)»: no la uses, porque no arranca en ninguna consola normal, ni siquiera
  modificada.

Los pasos:

1. Apaga la consola, saca el cartucho y quítale la microSD.
2. Conéctalo a la computadora con el cable. Debería aparecer una unidad nueva llamada RPI-RP2, como si
   fuera una memoria USB. Si no aparece, no sigas: mira [Si algo sale mal](#si-algo-sale-mal).
3. Copia el archivo `.uf2` en esa unidad y espera sin desconectar el cable.
4. Cuando termina, la unidad desaparece sola; puede tardar unos segundos. Puede volver a aparecer en
   seguida: es normal, porque el cartucho no tiene microSD.
5. Desconecta el cable y vuelve a meter la microSD. Con la consola apagada, mete el cartucho y
   enciéndela. Para que se abra Pico Launcher, la microSD tiene que tener sus archivos.

## Si algo sale mal

**El cartucho aparece en el menú, pero al abrirlo sale un error.** Mira
[Si tu DSi o tu 3DS dice «Se ha producido un error»](#si-tu-dsi-o-tu-3ds-dice-se-ha-producido-un-error).

**La consola no ve el cartucho, o se queda colgada al encenderla con él puesto.** Comprueba primero lo
fácil: la microSD dentro del cartucho y en FAT32, y la ranura limpia. Si es un DSpico USB-C de Phenom
Mod, la guía de Sanrax avisa de un fallo de su carcasa: con la consola encendida, aprieta el cartucho con
cuidado con el dedo; si entonces aparece, el problema es la carcasa. Si nada de eso lo explica, saca el
cartucho de la consola, quítale la microSD y conéctalo a la computadora. Si aparece la unidad RPI-RP2, el
cartucho responde. Comprueba que tu archivo es el de la variante que necesitas (nunca el de «Devkit») y
vuelve a seguir [Cómo se flashea](#cómo-se-flashea).

**No aparece la unidad RPI-RP2.**

1. Comprueba que el cartucho está fuera de la consola y sin la microSD.
2. Prueba con otro cable que transmita datos.
3. Usa el botón BOOTSEL. Es un botón muy pequeño, y se llega a él por un agujero en un lateral de la
   carcasa. La carcasa que diseñó el LNH Team tiene ese agujero; otras pueden no tenerlo. Si la tuya no
   lo tiene, no la abras ni le hagas uno. Si lo tiene, con el cable desconectado, mantén pulsado el botón
   con suavidad, sin forzar, conecta el cable y suéltalo. Así debería aparecer la unidad, aunque el
   firmware esté mal grabado.

Si ni con el botón aparece la unidad, prueba con más cables que transmitan datos. Si aun así no aparece,
no sigas probando por tu cuenta ni abras el cartucho: puede fallar el puerto USB o el propio cartucho.
Escribe al vendedor o pide ayuda en [r/flashcarts](https://www.reddit.com/r/flashcarts/), y cuenta qué has
probado.

Mientras consigas que aparezca la unidad RPI-RP2, un firmware mal grabado tiene arreglo: vuelve a copiar
el archivo correcto, aunque antes copiaras uno equivocado o la copia se cortara. No hemos encontrado
ningún caso de un DSpico que se quedara inservible por flashearlo.

## Fuentes

El DSpico es un proyecto del LNH Team, que publica gratis sus diseños y su código. Esta página se basa
sobre todo en su [guía oficial](https://github.com/LNH-team/dspico/blob/develop/GUIDE.md) y en la
[guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/). También usa
la [guía rápida de DS de flashcarts.net](https://www.flashcarts.net/ds-quick-start-guide), los
[planos del cartucho](https://github.com/LNH-team/dspico-hardware) del LNH Team, la
[ficha técnica del chip RP2040](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf) que
lleva el cartucho, [dsi.cfw.guide](https://dsi.cfw.guide/), [3ds.hacks.guide](https://3ds.hacks.guide/)
y casos de usuarios en r/flashcarts. Casi todas están en inglés.
