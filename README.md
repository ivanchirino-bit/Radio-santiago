# 📻 Dial Santiago

Aplicación web gratuita para escuchar radios chilenas en vivo, con foco en emisoras de Santiago. Sin anuncios, sin instalación, sin cuentas — solo abrir el link y darle play.

🔗 **[Escuchar ahora](https://ivanchirino-bit.github.io/Radio-santiago/)**

## ¿Qué es esto?

Dial Santiago reúne en un solo lugar las principales radios de Santiago y Chile, con reproducción directa dentro de la misma página. Nació como un proyecto simple para escuchar radio chilena desde cualquier navegador, sin depender de apps de terceros.

## Características

- 🎛️ Dial FM de Santiago (88–108): arrastra la aguja o usa ⏮ ⏭ para saltar de emisora
- 🎧 Reproducción directa, con señales de respaldo automáticas si la principal falla
- 🌐 Enlace a la web oficial de cada radio (y radios que solo se escuchan en su web)
- ⭐ Favoritas y filtros por categoría (Noticias, Rock, Romántica, Regiones…)
- 🔍 Buscador por nombre, frecuencia, género o ciudad
- 🌙 Temporizador de sueño (15 min a 2 horas)
- 📱 Controles en la pantalla de bloqueo del celular y modo oscuro automático
- ➕ Agregar emisoras propias (se guardan solo en tu navegador)
- ⚡ Sin frameworks: HTML, CSS y JavaScript puro en un solo archivo

## Emisoras disponibles

Radio Bío Bío, Radio La Clave, Cooperativa, ADN Radio, Radio Corazón, Radio Futuro, Radio Concierto, Radio Activa, Radio Pudahuel, Rock & Pop, FMDOS, Los 40, Radio Carolina, Radio Agricultura, Radio Duna, Radio Romántica, Radio Imagina, Tele13 Radio, Bío Bío Concepción, Radio Candela y Radio Carabineros.

## Cómo agregar una nueva radio

1. Abre `index.html` en el editor de GitHub
2. Busca el bloque `var STATIONS = [ ... ]` (al inicio del `<script>`, con instrucciones en un comentario)
3. Copia un bloque `{ ... },` existente, pégalo antes de `];` y cambia los datos:
   ```js
   { id: 'radio_nueva', name: 'Radio Nueva', fm: '100.5', city: 'Santiago', region: 'Metropolitana',
     genre: 'Pop & Éxitos', slogan: 'Frase corta', color: '#3F51B5',
     stream: 'https://URL_DEL_STREAM', backups: [],
     site: 'https://sitio-oficial.cl' },
   ```
4. Guarda los cambios ("Commit changes") — el sitio se actualiza solo en 1-2 minutos

- Si no tienes la URL de transmisión directa, pon `stream: null`: la emisora aparece con la etiqueta "Solo en su web" y abre su sitio oficial.
- Si la radio no tiene frecuencia en Santiago, pon `fm: null` y un `badge` corto (ej. `badge: 'CUM'`).
- Ojo con las comas: cada bloque termina en `},` (salvo el último de la lista).

## Tecnología

Proyecto 100% estático: un solo archivo `index.html` con HTML, CSS y JavaScript vanilla (más hls.js desde cdnjs para las señales .m3u8). No requiere build, servidor backend ni base de datos. Desplegado con [GitHub Pages](https://pages.github.com/).

## Créditos

Fuentes de transmisión obtenidas de los sitios oficiales de cada radio y de [myradioonline.cl](https://myradioonline.cl).

---

Proyecto personal, sin fines comerciales. Todas las marcas y transmisiones pertenecen a sus respectivas radios.
