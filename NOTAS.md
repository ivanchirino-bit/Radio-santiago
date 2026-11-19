# Dial Santiago — Notas del proyecto

*Última actualización: 19 de noviembre de 2026*

App web gratuita para escuchar radios chilenas en vivo, con foco en Santiago. Es un solo archivo `index.html` (HTML, CSS y JavaScript sin frameworks), publicado en GitHub Pages.

## Dónde está todo

| Qué | Dirección |
|---|---|
| Sitio publicado | https://ivanchirino-bit.github.io/Radio-santiago/ |
| Repositorio | https://github.com/ivanchirino-bit/Radio-santiago |
| Artefacto en Claude (copia de respaldo, sin audio) | https://claude.ai/artifact/9c7WQiecaB1vkkJdtkfTMD |
| Repositorio antiguo (cuenta sin acceso) | https://github.com/ivanchirino-eng/Radio-santiago — quedó con la versión vieja |

- **El nombre del repositorio es `Radio-santiago`, con R mayúscula.** La dirección del sitio distingue mayúsculas y minúsculas.
- El artefacto tiene el `index.html` y el `README.md` como respaldo. En el visor de Claude las radios **no suenan**, porque bloquea el audio externo.
- Las favoritas, el volumen y las emisoras propias se guardan en el navegador **por dirección**. Al cambiar de dirección hay que marcarlas de nuevo.

## Historia

- **Radio Stgo / Dial Santiago (septiembre 2026):** primera versión. Lista simple con buscador y enlace a la web oficial de cada radio.
- **Radios de Chile:** versión hecha con Gemini y luego mejorada en Claude, con dial FM, favoritas y temporizador.
- **19 de noviembre de 2026:** se fusionaron las dos con el nombre **Dial Santiago**. La base es Radios de Chile, más las radios, los enlaces a la web oficial y las señales de Radio Stgo. Se publicó en la cuenta nueva `ivanchirino-bit`, porque se perdió el acceso a `ivanchirino-eng`.

## Funciones

- Dial FM de Santiago (88–108) con aguja que se arrastra. Los botones ⏮ ⏭ recorren el dial y después las radios online sin frecuencia (Candela).
- Al pasar el cursor por el dial, las barras de las radios se agrandan como el dock del Mac, brillan con el color de cada radio y aparece una etiqueta con la frecuencia y el nombre. Solo funciona con mouse.
- El analizador de espectro es **el doble de grande** y brilla con el color de la radio que suena. En el celular va en una fila propia, debajo de la frecuencia.
- "En vivo" parpadea con el color de la radio sintonizada, también en el mini reproductor.
- Favoritas: una **estrella ⭐ con halo neón amarillo que late** aparece a la derecha de la frecuencia en el sintonizador (por ejemplo **104.1 FM ⭐**). En la lista no se muestra.
- Si la señal principal falla, prueba sola las señales de respaldo. Si fallan todas, muestra "Reintentar" y "Escuchar en su web".
- Filtros, buscador, temporizador de sueño, controles en la pantalla de bloqueo, modo oscuro automático y emisoras propias (se guardan solo en el navegador).
- Si el equipo tiene activado "reducir movimiento", las animaciones se desactivan.

## Decisiones tomadas

- **Radio Carabineros va en el 98.1 del dial y es la primera de la lista.** Es una posición elegida para la app: Carabineros no transmite en esa frecuencia en Santiago. Bío Bío Concepción también aparece con 98.1 en la lista, pero no está en el dial, así que no chocan.
- Solo aparecen en el dial las radios con `city: 'Santiago'` y frecuencia.
- La lista de emisoras usa un bloque `{ ... }` por radio, con los campos explicados al inicio del `<script>`, para poder editarla fácil desde el editor de GitHub en el celular.

## Señales (21 emisoras)

ST = `https://playerservices.streamtheworld.com/api/livestream-redirect/`

| Radio | Dial | Señal principal | Respaldos |
|---|---|---|---|
| Radio Carabineros | 98.1* | `https://streaming.prositel.cl/8374/stream` | — |
| Radio Bío Bío | 99.7 | `redirector.dps.live/biobiosantiago/mp3/icecast.audio` | 2 (servidores unlimited3-cl y unlimited5-us) |
| **Radio La Clave** | 92.9 | `https://redirector.dps.live/laclave/aac/icecast.audio` | `unlimited3-cl.dps.live/laclave/aac/icecast.audio` y la señal de video `laclavetv` |
| Radio Cooperativa | 93.3 | `redirector.dps.live/cooperativafm/mp3/icecast.audio` | 3 (versión aac y servidores unlimited) |
| ADN Radio Chile | 91.7 | ST + `ADN_SC` | ST + `ADNAAC.aac` |
| Radio Corazón | 101.3 | ST + `CORAZON_SC` | — |
| Radio Futuro | 88.9 | ST + `FUTURO_SC` | ST + `FUTUROAAC.aac` |
| Radio Concierto | 88.5 | ST + `CONCIERTO_SC` | ST + `CONCIERTOAAC.aac` |
| Radio Activa | 92.5 | ST + `ACTIVA_SC` | — |
| Radio Pudahuel | 90.5 | ST + `PUDAHUEL_SC` | ST + `PUDAHUELAAC.aac` |
| Radio Rock & Pop | 94.1 | ST + `ROCK_AND_POP_SC` ⚠️ | — |
| Radio FMDOS | 98.5 | ST + `FMDOS_SC` | — |
| Los 40 Chile | 101.7 | ST + `LOS40_CHILE_SC` | — |
| Radio Carolina | 99.3 | `mdstrm.com/audio/63a06468117f42713374addd/icecast.audio` | `live.m3u8` del mismo ID y el ID antiguo `637f68ddce4b1208597d8a86` |
| Radio Agricultura | 92.1 | HLS en `jireh-1-hls-audio-cl-isp.dps.live/…/agricultura/…/livestream1.m3u8` | rudo.video y `unlimited5-us.dps.live/agricultura/…` |
| Radio Duna | 89.7 | `mdstrm.com/audio/67f42f96e464d19a6eda3c7d/icecast.audio` | — |
| Radio Romántica | 104.1 | `mdstrm.com/audio/639b78f7ff35df084fa7f964/icecast.audio` | `live.m3u8` del mismo ID |
| Radio Imagina | 88.1 | ST + `IMAGINA_SC` ⚠️ | ST + `IMAGINAAAC_SC` |
| **Tele13 Radio** | 103.3 | `https://mdstrm.com/audio/5c915613519bce27671c4caa/icecast.audio` | `live.m3u8` del mismo ID |
| Radio Bío Bío Concepción | (98.1 Concepción, fuera del dial) | `redirector.dps.live/biobioconcepcion/mp3/icecast.audio` | 2 |
| Radio Candela | online (CUM) | HLS en `redirector.rudo.video/…/candela/candela.smil/playlist.m3u8` | — |

\* Posición elegida para la app, no es la frecuencia real.
⚠️ Señal sin comprobar.

### Cómo se encontraron las últimas

- **Tele13 Radio:** el reproductor de tele13radio.cl usa Mediastream. El ID de la transmisión en vivo (`5c915613519bce27671c4caa`) sale en las peticiones a `mdstrm.com/live-stream/<ID>.json`. Con ese ID funcionan `mdstrm.com/audio/<ID>/icecast.audio` y `/live.m3u8`. Comprobado el 19 de noviembre de 2026.
- **Radio La Clave:** la web radiolaclave.cl solo muestra video (`pantera1-100gb-cl-movistar.dps.live/laclavetv/laclavetv.smil/playlist.m3u8`). Probando los formatos de dps.live funcionan `redirector.dps.live/laclave/aac/icecast.audio` y `unlimited3-cl.dps.live/laclave/aac/icecast.audio`. No funcionan la versión `mp3` ni `unlimited5-us`. Comprobado el 19 de noviembre de 2026.

### Truco para buscar una señal

1. Abrir la web oficial de la radio y darle play.
2. En las herramientas del navegador, pestaña **Network** (Red), buscar `m3u8`, `icecast`, `mdstrm`, `dps.live`, `streamtheworld` o `rudo.video`.
3. Patrones conocidos:
   - Mediastream: `https://mdstrm.com/audio/<ID>/icecast.audio`
   - dps.live: `https://redirector.dps.live/<nombre>/aac/icecast.audio` (o `/mp3/`)
   - StreamTheWorld: `ST + 'NOMBRE_SC'` o `ST + 'NOMBREAAC.aac'`
4. Fuente útil: myradioonline.cl.
5. El enlace tiene que empezar con **https://**, porque el navegador bloquea las señales `http://` en una página segura.

## Pendiente

- [ ] Comprobar o reemplazar las señales de **Rock & Pop** e **Imagina**.
- [ ] Revisar que la versión `aac` de Cooperativa siga funcionando como respaldo.
- [ ] Idea de más adelante: versión nativa para iOS cuando la web esté estable.

## Cómo actualizar el sitio

1. Editar `index.html` en GitHub, en el repositorio `ivanchirino-bit/Radio-santiago`, o reemplazarlo con **Add file → Upload files**.
2. **Commit changes.** El sitio se actualiza en 1 o 2 minutos.
3. Si el sitio muestra un error 404: en **Settings → Pages** revisar que la rama sea **main** y la carpeta **/ (root)**.
