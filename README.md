# 10Y7 Sensitivity — v2.0.0 RC2

Versión de prueba previa a publicación. Aplicación estática compatible con Cloudflare Pages, sin npm ni compilación. Mantiene el asistente inicial, conversor, catálogo, buscador, historial y perfil de la web v1.

## Novedades
- Dashboard con perfil lateral, juegos ilustrados, estadísticas, niveles y XP calculados a partir de sesiones guardadas.
- Avatar y banner personalizados, color, brillo, redondez, densidad, bio, región, marcos y logros.
- Rango angular 3D basado en perspectiva, independiente del buscador: Static click, Dynamic click, Smooth tracking, Reflex shot, Precision dots, Burst switching y 180° turn. Duración, FOV horizontal, dificultad, escenario y color configurables. Editor de mira con previsualización y presets. Rutinas rápidas por juego.
- Historial filtrable, precisión, puntuación, racha, mapa de errores de disparos, reacción media y combo. Las sesiones 3D interrumpidas no se guardan. Comparar únicamente sesiones equivalentes. El navegador puede aplicar aceleración y no reproduce los motores de juego exactamente.
- Presets de sensibilidad y respaldo integral local. La importación reemplaza datos después de confirmación. Los datos no se sincronizan entre dominios automáticamente.
- Sin registro, autenticación ni sincronización online. Los perfiles, preferencias e historial se conservan localmente en el navegador. Algunas imágenes se cargan desde proveedores externos.

## Imágenes y atribuciones
Los gráficos vectoriales locales son originales de la app. Las tarjetas intentan cargar arte promocional de Valorant (Riot Games), Counter-Strike 2 (Steam/Valve) y Fortnite (Epic Games); si no está disponible, mantienen los gráficos locales. Las imágenes externas necesitan conexión y su disponibilidad no se ha validado desde el entorno de desarrollo. Las marcas pertenecen a sus respectivos propietarios. Proyecto independiente, no afiliado ni respaldado por esos editores. Antes de distribuir, verificar permisos de uso y condiciones de los editores.
- https://playvalorant.com/en-us/news/game-updates/valorant-asset-kit/
- https://store.steampowered.com/app/730/CounterStrike_2/
- https://store.epicgames.com/en-US/p/fortnite--battle-royale
- https://legal.epicgames.com/epicgames/fan-art-policy

## Probar sin publicar
Descomprime todo. Puedes abrir index.html para ver la interfaz, aunque la captura del mouse y el modo offline dependen del navegador y del origen. Recomendado: desde esta carpeta ejecutar `python -m http.server 8000` y abrir http://localhost:8000/ en Chrome o Edge. El modo PWA requiere localhost o HTTPS.

## Validación
Se comprobó sintaxis de JavaScript y se realizaron pruebas de interfaz con Chromium sobre HTML incorporado y almacenamiento simulado: conversión Valorant a CS2, avatar, colores, sesión básica y guardado, selector de nuevos modos, editor de mira, presets, estadísticas, y adquisición de Pointer Lock estándar por el rango angular. No se ha validado la precisión física del mouse, una sesión 3D completa en producción, la captura sin aceleración, el service worker por HTTPS ni las imágenes externas. La navegación por servidor local está bloqueada en el entorno de pruebas.

## Publicar (solo después de aprobar)
Subir todos los archivos web y `assets/` a la raíz de 10y7/10Y7-Sensitivity. Preferir una rama de prueba y comprobar la URL de preview antes de mezclarla a main. Cloudflare Pages: framework None, build vacío, output `.`. Los archivos de documentación no son requeridos por el navegador. El service worker cambia su nombre de caché en esta versión.

## Cambiar URL
Exportar todo desde Apariencia > Respaldo completo antes de cambiar el dominio. Crear el nuevo proyecto de Cloudflare Pages conectado al mismo repositorio, probarlo e importar el respaldo. Conservar el sitio anterior hasta verificar que todo funciona.
