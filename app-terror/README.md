# 💀 Noche de Terror

App web con **15 sonidos de terror** para Halloween: gritos, demonios,
susurros, puertas que rechinan y más.

## Cómo usarla

Abre el link en cualquier navegador (celular, tablet o computadora).
Es un solo archivo: no necesita instalación ni servidor, y los sonidos
funcionan sin internet (solo la letra del título se descarga de Google Fonts).

En el celular puedes agregarla a la pantalla de inicio (Compartir → "Añadir a
pantalla de inicio").

## Qué trae

Cada sonido **se repite sin parar hasta que lo vuelvas a tocar**, y puedes
tener varios sonando a la vez (por ejemplo latido + susurros + grito).

**10 sustos**:
grito desgarrador, demonio, risa de bruja, zombi, aullido de lobo,
puerta que rechina, golpes en la puerta, cadenas, violines asesinos y campanadas.

**5 ambientes** de fondo:
susurros, latido de pánico (se acelera), respiración en la nuca,
caja de música maldita y casa embrujada.

**💀 Susto sorpresa**: eliges cuánto esperar (10 s, 30 s, 1 min o al azar),
dejas el celular escondido con la pantalla en negro y, cuando nadie lo espera,
suelta un grito con violines y un golpe grave a todo volumen. Toca la pantalla
negra para cancelar.

## Cómo funciona por dentro

Igual que la app "Duerme Bebé": **no hay archivos de audio**. Todo se sintetiza
en el momento con la Web Audio API del navegador.

- **Las voces** (grito, demonio, bruja, zombi, lobo, fantasma) imitan una
  garganta: una vibración (onda "diente de sierra" + aire) pasa por
  **formantes**, filtros que hacen el papel de la boca y dan la vocal.
- **El truco del miedo es la "aspereza"**: el volumen tiembla entre 30 y 150
  veces por segundo. Los estudios sobre gritos humanos muestran que ese temblor
  rápido es lo que el cerebro reconoce como alarma.
- **El demonio** son tres voces a la vez: una grave, la misma una octava más
  abajo y un chillido escondido arriba, todo con distorsión.
- **La puerta** son cientos de golpecitos por segundo (la bisagra que se atasca
  y suelta) que hacen vibrar filtros muy resonantes, como la madera.
- **Las cadenas** son eslabones: cada uno es una campanita de 4 tonos que se
  apaga en milisegundos.
- **La caja de música maldita** es "Estrellita" (la de la app de la bebé) en
  tono menor, desafinada y cada vuelta más lenta y más grave.
- **Los ambientes** usan un "programador": cada 250 ms agenda los eventos del
  siguiente segundo con el reloj del audio (`ctx.currentTime`), que es mucho
  más preciso que `setTimeout`.
- Un **limitador** al final deja subir el volumen sin que el altavoz distorsione.

## Úsalo con responsabilidad

No asustes a personas con problemas del corazón, bebés ni mascotas.
