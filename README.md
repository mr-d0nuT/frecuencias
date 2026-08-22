# Frecuencias

Cuadro de consulta de las frecuencias de radio utilizables en España.

👉 **[Abrir la app](https://mr-d0nut.github.io/frecuencias/)**

Archivo único, sin dependencias, funciona sin conexión: descarga
[`index.html`](https://github.com/mr-d0nuT/frecuencias/raw/refs/heads/main/index.html)
y ábrelo con doble clic. En el móvil se puede añadir a la pantalla de inicio
desde el navegador y queda como una app más.

## Qué hace

**44 bandas del CNAF con RX y TX valorados por separado.** Escuchar y
transmitir tienen legalidad y riesgo independientes, y confundirlos es el
error más común de las guías al uso. Escuchar la banda aérea no es
infracción; emitir en ella es crítico. Cada banda lleva las dos
valoraciones, su potencia máxima, sus modos y sus canales completos:
CB-27, PMR446, dPMR446, LPD433, marina VHF con dúplex y AIS, WiFi,
radiocontrol y las 21 bandas de radioaficionado.

**72 aeródromos y helipuertos españoles.** Eliges uno y la app descarga el
documento AD 2.18 del AIP de ENAIRE y lo interpreta en el navegador,
mostrando torre, ATIS, rodadura y aproximación con la enmienda vigente.

Además: buscador por frecuencia, mapa logarítmico del espectro, filtros
cruzados, favoritos, tema claro/oscuro e interfaz específica para móvil.

## El extractor de PDF

`aipx` es un extractor de PDF escrito desde cero, sin librerías, unas 350
líneas embebidas en la propia página. Descomprime con `DecompressionStream`
(nativo del navegador), recorre los objetos, decodifica los CMap
`/ToUnicode`, usa las anchuras reales de glifo para distinguir un espacio de
una letra ancha, reconstruye la tabla por coordenadas y aísla la sección de
comunicaciones.

Cubre las dos generaciones de PDF del AIP: los modernos con object streams y
fuentes subset, y los bilingües antiguos con fuentes Type1, escapes octales
y continuaciones de línea.

Convierte los canales de 8,33 kHz a portadora real: el AIP publica `128.880`,
tu escáner necesita `128,875 MHz`.

## Tolerancia a fallos

- Copia local de los 72 aeródromos embebida: respuesta instantánea y
funcionamiento sin conexión.
- Caché de siete días en el navegador.
- Tiempo máximo de espera de 25 s; nunca se queda colgada.
- Si la lectura en vivo sale más pobre que la copia local, gana la copia
local: nunca muestra menos información de la que tiene.

Cobertura: 69 de 72. Los otros tres publican literalmente *Information not
available* en el AIP, y la app lo dice en vez de mostrar una tabla vacía.

## Aviso

Guía de consulta, no fuente oficial. La referencia vinculante es el CNAF
vigente y el AIP de ENAIRE. Las frecuencias cambian por enmienda: contrasta
antes de operar. Hay enlace al PDF oficial junto a cada tabla.

Fuera de las bandas de uso común, transmitir sin título habilitante es
infracción de la Ley General de Telecomunicaciones. La escala de riesgo
sirve para entender el daño de cada caso y elegir la alternativa legal, no
para relativizar el incumplimiento.
