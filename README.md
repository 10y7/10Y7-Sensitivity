# 10Y7 Sensitivity — v2.1.0 beta (Competitive Aim Update)

Aplicación web estática, local y gratuita; sin cuentas. No requiere npm ni proceso de compilación. Basada en RC2 local.

## Publicar en la rama de pruebas
1. Descomprimir el ZIP. En GitHub abrir `10y7/10Y7-Sensitivity` → rama `v2-preview` → Add file → Upload files.
2. Subir el contenido de la raíz (incluida `assets/`). Confirmar que `index.html`, `competitive.js`, `competitive.css` y `sw.js` están en la raíz. Hacer commit en `v2-preview`, no `main`.
3. En Cloudflare Pages comprobar Deployments → Preview → v2-preview. Abrir la URL que Cloudflare indique. Si se muestra el código anterior, abrir una ventana privada. El menú indica V2.1.0 · COMPETITIVE BETA.
4. Para publicar en producción, abrir un pull request de v2-preview a main una vez probados los entrenadores. No se cambia la configuración de Cloudflare.

## Novedades
- 12 escenarios Canvas 2D y 11 escenarios 3D, con mallas de esferas y sala de líneas WebGL. Si WebGL no está disponible se ofrece proyección Canvas identificada como compatibilidad. Modos, favoritos, récords por escenario/renderer/duración/FOV/escala vertical, rutinas y ajustes libres.
- Rango físico: conversión de cuentas a ángulos según DPI y cm/360; se solicita Pointer Lock sin aceleración, con respaldo estándar. El 2D es un plano con mira móvil (no una reproducción de un FPS); el 3D utiliza cámara y detección de intersección geométrica. R reinicia; Esc detiene. WASD en Movement Aim.
- Buscador guiado: base y candidatos, tareas comparables con semillas compartidas, ponderación por juego y objetivo, 50% rendimiento y 50% comodidad. Refinamiento alrededor del mejor. La recomendación es una prueba inicial y requiere validación en el juego. Los datos de hardware son contexto, no predictores exactos de rendimiento. El antiguo panel manual sigue disponible.
- FiveM: solo cm/360 medidos. Guarda valores reales del comando `profile_mouseOnFootScale`, DPI y contexto y busca la medición más cercana. El valor inicial 40 cm/360 es un ejemplo editable, no una calibración. No se afirma equivalencia universal del comando.
- Apariencia independiente: seis temas, controles de acento, redondez, brillo, densidad, fondos, tipografía, animaciones, perfil lateral, mira, sonido, cuadrícula y HUD; importación/exportación de tema. El avatar y banner se editan en Mi perfil.
- Tarjetas de juego con enlaces de arte promocional comprobados en fuentes de Riot Games, Valve y Epic Games, y gráficos locales de respaldo. No se pudieron descargar originales al entorno de construcción. FiveM conserva tarjeta gráfica local no oficial. No se garantiza disponibilidad de los recursos externos; no se sustituyen por una imagen rota. Proyecto no afiliado a estos editores. Ver ASSETS.md.
- Conserva las claves de almacenamiento de RC2 y añade las de v2.1. Respaldo en perfil. Los datos de la URL de pruebas y producción son independientes por origen.

## Pruebas efectuadas
- `node --check`: scripts externos e inline.
- Chromium con HTML/CSS/JS cargados en un documento de prueba (navegación local bloqueada): seis pantallas, 12 y 11 tarjetas de escenarios, creación de plan, guardado de calibración FiveM y navegación.
- Pruebas de flujo con captura y reloj simulados: finalización y guardado de sesión 2D, 3D en compatibilidad, avance de búsqueda guiada; sin excepciones de página en esas pruebas.
- Pendiente: captura física real del mouse, precisión comparada con juegos, WebGL en GPU real, imágenes remotas en Cloudflare, service worker e instalación PWA en HTTPS. No considerar versión estable hasta probarlo.

Prueba local normal: servir la carpeta con `python -m http.server 8000` y abrir http://localhost:8000. En Cloudflare Pages: framework None, build vacío, output `.`. La PWA requiere HTTPS o localhost.
