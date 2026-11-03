---
title: "Antes de comprar"
BookIcon: carrito
weight: 10
versions: ["Pico Launcher 1.3.0", "Pico Loader 1.7.1", "Firmware oficial 1.0.1"]
reviewed: 2026-11-01
---

El DSpico es un cartucho flash para la DS que también funciona en la DSi y la 3DS, con una ranura para
una tarjeta microSD. En una DSi o una 3DS sin modificar no todos los DSpico funcionan: si es tu caso, mira
antes de pagar [Qué mirar antes de comprar](#qué-mirar-antes-de-comprar). Qué programas usa lo explica la
[página del DSpico](_index.md).

## Qué hace y qué no hace

Con el DSpico, la consola abre los juegos de DS que copies en la microSD, y también programas caseros
(homebrew). Según el LNH Team, debería funcionar la mayoría de los juegos de DS, pero no tiene una lista
de compatibilidad y sabe de algunos que todavía fallan. Admite trucos y portadas en el menú, pero el
archivo de trucos y las imágenes de las portadas los pones tú. Las partidas se guardan en la microSD, así
que te las llevas con el cartucho a otra consola.

En una DSi o una 3DS funciona además en modo DSi, con lo que la DSi tiene de más que la DS: los juegos con
mejoras de DSi, como los que usan la cámara, las aprovechan, y se puede abrir DSiWare, los juegos y
programas que se descargaban de la tienda de la DSi. Para DSiWare hace falta copiar antes unos archivos de
tu propia consola, y esta guía no lo explica. En una DS o una DS Lite no hay modo DSi: ni mejoras de DSi
ni DSiWare.

Lo que no hace:

- No abre juegos de 3DS, tampoco en una 3DS.
- Los juegos de GBA no se abren sin más. La DS y la DS Lite tienen otra ranura, abajo, para los cartuchos
  de GBA, pero el DSpico va en la de DS: para abrir juegos de GBA desde la microSD hace falta un emulador
  aparte y configurarlo, y no todos los juegos van bien.
- Pico Loader todavía no permite volver al menú desde un juego: hay que guardar la partida y apagar la
  consola.
- El menú solo está en inglés.
- El DSpico, tal como lo diseña el LNH Team, no tiene infrarrojos. Por eso no funciona lo que en algunos
  juegos va por infrarrojos, como conectar Pokémon Oro HeartGold y Plata SoulSilver con el Pokéwalker.
  Si un anuncio dice que tiene infrarrojos, es otro diseño, de otro fabricante, como el «DSpico IR», o
  el anuncio se equivoca.
- No trae juegos, y en esta guía no se dice dónde conseguirlos.

## En qué consolas funciona

En una DS y una DS Lite funciona sin modificar ni «liberar» la consola, lleve el firmware que lleve (el
programa grabado en el cartucho). Eso sí, tiene que traer alguno: si llega sin firmware, no funciona en
ninguna consola.

En una DSi o una DSi XL y en cualquier 3DS o 2DS (también las New y las XL) funciona con cualquier versión
del sistema, pero depende del firmware que lleve. Hay dos variantes: WRFUxxed funciona en todas, y Hybrid
solo en las que están modificadas, con Unlaunch en la DSi o con un sistema modificado (CFW) en la 3DS.
Una DSi con TWiLight Menu++ pero sin Unlaunch no cuenta como modificada. Si no sabes si tu consola lo
está, la que te sirve seguro es WRFUxxed. Lo explican [Las dos variantes](firmware.md#las-dos-variantes)
y [Qué cuenta como modificada](firmware.md#qué-cuenta-como-modificada).

En una 3DS, Nintendo dice que los juegos de DS se ven a menor resolución que los de 3DS, y que para verlos
a su resolución original hay que mantener pulsado START o SELECT al abrirlos. Con el DSpico usa solo
SELECT, sin START: un usuario avisó al LNH Team de que, con WRFUxxed, mantener START hace que la consola se
reinicie una y otra vez mientras no lo sueltes.

## ¿DSpico o R4?

«R4» es el nombre de muchos cartuchos distintos. Hay muchísimos clones, a menudo con su propio menú, y lo
que sirve para uno no siempre sirve para otro. Las copias exactas de la R4 original solo admiten microSD
de 2 GB o menos y no funcionan en una DSi ni en una 3DS sin modificar. Otros clones, como los Ace3DS+ y
R4iLS de más abajo, funcionan en todas.

Algunos traen una «bomba de tiempo»: pasada una fecha, muestran un error y no dejan entrar al menú. No
borran tus archivos ni dañan el cartucho o la consola, y tiene arreglo. La wiki en inglés flashcarts.net,
que no es del LNH Team, dice en su
[página sobre la bomba de tiempo](https://www.flashcarts.net/ds-timebomb) qué modelos la tienen y cómo
evitarla.

Lo que tiene el DSpico:

- Pico Launcher y Pico Loader reciben actualizaciones, y se ponen gratis copiando sus archivos en la
  microSD. El diseño y el código del DSpico son públicos: Dartz, del LNH Team, contó que lo hicieron para
  no depender de cartuchos que nunca se actualizan.
- En una DSi o una 3DS arranca en modo DSi. Los demás cartuchos que se venden hoy arrancan en modo DS, y
  por eso no pueden usar las funciones de DSi.

Si ya tienes una R4 que te funciona, puede que Pico Launcher y Pico Loader funcionen en ella: Pico Loader
admite muchos otros cartuchos. Según Gericom, autor principal de Pico Launcher y Pico Loader, la
diferencia con usarlos en un DSpico es poca: como mucho algo de velocidad al leer la microSD, y que los
otros cartuchos no tienen el modo DSi. Lo dijo de los cartuchos en los que Pico Loader usa un modo de
lectura más rápido (DMA). En las copias de la R4 original no lo usa, y su documentación avisa de que
entonces algunos juegos pueden fallar. Pico Loader trae un zip para cada familia de cartuchos, y sus
autores avisan de que el equivocado puede dañar el cartucho. Hay muchísimos clones de R4 y no es fácil
saber de qué familia es la tuya: si no lo sabes seguro, no lo pruebes. En un DSpico, aunque vaya en una
carcasa de R4, usa siempre el zip del DSpico.

Si solo quieres jugar a juegos de DS, la guía de flashcarts.net llama a los clones Ace3DS+ y R4iLS la
opción más recomendada: funcionan en todas las DS, DSi y 3DS, también sin modificar y con la última
versión del sistema, y suelen ser más baratos que el DSpico. A cambio, no tienen modo DSi, sus carcasas
encajan mal en algunas consolas y su menú no trae los arreglos que necesitan algunos juegos, como Pokémon
Negro 2 y Blanco 2.

## ¿DSpico o TWiLight Menu++?

TWiLight Menu++ es un menú casero que se instala en la propia DSi o 3DS y, con nds-bootstrap, abre los
juegos de DS desde la tarjeta SD de la consola, sin cartucho. Para instalarlo, la 3DS tiene que estar
modificada (CFW), y la DSi necesita antes un método para abrir programas caseros; esta guía no explica
cómo. El DSpico con WRFUxxed no pide tocar la consola. Si ya tienes TWiLight Menu++, puede que no
necesites cartucho: la guía de flashcarts.net aconseja probar eso primero, y comprar un cartucho solo si
un juego no te funciona o si quieres llevar tus juegos y tus partidas de una consola a otra.

- Con TWiLight Menu++ instalado en la consola, abriendo los juegos desde su tarjeta SD, puedes volver al
  menú desde un juego: mantén pulsados L, R, abajo y B durante dos segundos.
- Con un cartucho, según flashcarts.net, funcionan algunos juegos de DS más que con nds-bootstrap. Y te
  llevas juegos y partidas a cualquier consola, también a una DS o una DS Lite.

No hay que elegir uno: TWiLight Menu++ también funciona en el DSpico. Pero desde el cartucho no cuentes
con esa combinación de botones: en una DS o una DS Lite no funciona, y en una DSi o una 3DS no lo hemos
podido comprobar.

## ¿Original o falso?

El LNH Team no vende el DSpico ni recomienda ninguna tienda. Publica el diseño para que cualquiera lo
fabrique, y todos los que se venden los hacen tiendas sin relación con él. El LNH Team avisa de que no
puede garantizar la calidad del cartucho que te llegue. Así que no hay un DSpico «oficial» a la venta, y
que lo venda una tienda no lo hace «pirata»: la licencia del diseño permite fabricarlo y venderlo. Lo más
parecido a uno oficial es uno hecho con el diseño que publica el LNH Team, que lleva puerto micro USB.

No hemos encontrado ningún caso de una R4 ni de otro cartucho vendido con la etiqueta del DSpico. Estas
cosas han hecho dudar a algunos compradores:

- Versiones recortadas, como el «DSpico Lite» o los que van en una carcasa tipo Ace3DS+. No suelen tener
  puerto USB, así que su firmware no se puede cambiar, y suelen encajar mal en la ranura de algunas
  consolas, igual que los Ace3DS+. La guía de flashcarts.net aconseja evitarlos.
- Versiones con USB-C o con otra carcasa. No son falsas: son variaciones de otros fabricantes.
- Webs que se presentan como la oficial del DSpico, con el logo del LNH Team, y te mandan a comprar. No
  son del LNH Team: su web es [lnh-team.org](https://www.lnh-team.org/) y no vende nada. Que un anuncio
  diga que el diseño es del LNH Team es normal, porque lo es; lo que no es cierto es que el LNH Team lo
  venda.

## Qué mirar antes de comprar

- Que tenga puerto USB. Da igual que sea micro USB o USB-C: solo cambia el cable. Sin puerto, el firmware
  que traiga no se puede cambiar: si no sirve para tu consola, se queda así.
- Con qué firmware llega. Según la guía de Sanrax, la mayoría de los que se venden en AliExpress y otras
  tiendas llegan grabados, muchas veces con WRFUxxed; algunas tiendas avisan en su anuncio de que lo
  envían sin firmware, y así no funciona en ninguna consola. Si lo vas a usar en una DSi o una 3DS sin
  modificar, pregunta al vendedor antes de pagar si llega con WRFUxxed. Si llega con Hybrid o sin
  firmware, en esas consolas no funcionará: para grabarle WRFUxxed hace falta tu propia copia de un
  programa de pruebas de Nintendo, y no te recomendamos modificar la consola solo para esto. Lo explica
  [Si tu DSi o tu 3DS dice «Se ha producido un error»](firmware.md#si-tu-dsi-o-tu-3ds-dice-se-ha-producido-un-error).
- La carcasa. La guía de flashcarts.net dice que las de plástico moldeado por inyección son mejores que
  las impresas en 3D, aunque a la mayoría le sirven las dos.
- No cuentes con la microSD que venga en el paquete: compra aparte una de marca, como explica
  [Qué necesitas](primeros-pasos.md#qué-necesitas). Para no comprar una falsa, flashcarts.net aconseja
  comprarla en tiendas de confianza y de marcas conocidas, y no comprarla en AliExpress, Temu, Shein ni
  Wish. También avisa de que las de marca Xiaomi, Mi o Huawei suelen ser falsas, porque esas marcas no
  venden microSD. Explica cómo probarla en su
  [página sobre microSD falsas](https://www.flashcarts.net/microsd-fakes) (en inglés). Las de 4 a 32 GB
  son las más fáciles de preparar: lo explica [La microSD](primeros-pasos.md#la-microsd).
- Que tengas una computadora (un PC o un ordenador) en la que puedas meter la microSD, con un lector de
  tarjetas o un adaptador. La tarjeta se prepara ahí: desde el celular, una tablet o un Chromebook no es
  fiable.

## Dónde comprarlo

Ni nosotros ni el LNH Team recomendamos tiendas. La
[guía rápida de DS](https://www.flashcarts.net/ds-quick-start-guide) de flashcarts.net (en inglés) tiene
su propia lista de enlaces de compra. También aconseja no comprar en webs que llevan «R4» en el nombre,
porque suelen ser estafas y no devuelven el dinero. En el anuncio, mira bien qué opción eliges: en
r/flashcarts contaron el caso de un anuncio de AliExpress en el que la opción más barata era solo la
carcasa, sin el cartucho.

## Cuando te llegue

1. Sin una microSD en FAT32 dentro no funciona: la consola no lo ve o se queda colgada al encenderla.
   Antes de probarlo, prepara la microSD como explica [Primeros pasos](primeros-pasos.md).
2. Si tienes una DSi o una 3DS, mira cuanto antes qué variante de firmware trae:
   [Qué variante lleva tu cartucho](firmware.md#qué-variante-lleva-tu-cartucho). Si no es la que pediste,
   reclama al vendedor mientras estés a tiempo.
3. Si no aparece en ninguna consola, revisa primero la microSD y la ranura, como explica
   [¿Necesito flashearlo?](firmware.md#necesito-flashearlo). Si sigue sin aparecer, puede que haya llegado
   sin firmware: escribe al vendedor antes de intentar grabarlo tú.

## Fuentes

Esta página se basa en el [repositorio del hardware](https://github.com/LNH-team/dspico-hardware), la
[web](https://www.lnh-team.org/) y el código y la documentación de
[Pico Launcher](https://github.com/LNH-team/pico-launcher) y [Pico Loader](https://github.com/LNH-team/pico-loader)
del LNH Team, y en lo que sus miembros y colaboradores contestan en el
[hilo del DSpico en GBAtemp](https://gbatemp.net/threads/dspico-an-open-source-flashcart-for-the-ds-i.677498/),
en GitHub y en YouTube. También usa la
[guía rápida de DS](https://www.flashcarts.net/ds-quick-start-guide) y otras páginas de flashcarts.net,
la [guía del DSpico de Sanrax](https://sanrax.github.io/flashcart-guides/cart-guides/dspico/), las
[preguntas frecuentes de dsi.cfw.guide](https://dsi.cfw.guide/faq.html), la
[wiki de TWiLight Menu++](https://wiki.ds-homebrew.com/twilightmenu/installing-flashcard), la
[wiki de nds-bootstrap](https://wiki.ds-homebrew.com/nds-bootstrap/), la
[ayuda de Nintendo](https://en-americas-support.nintendo.com/app/answers/detail/a_id/324) y casos de
usuarios en r/flashcarts y GBAtemp. Casi todas están en inglés.
