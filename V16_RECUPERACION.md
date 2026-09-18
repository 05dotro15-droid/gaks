# GAKS V16 — recuperación

Base: V13 estable. No usa V15 como base.

Cambios:
- Se evita modificar los grandes bloques JavaScript del index.
- Todas las correcciones nuevas van en `gaks-v16-patches.js`.
- Permiso POST_NOTIFICATIONS declarado explícitamente.
- Puente nativo Android `GaksAndroid` para:
  - consultar si las notificaciones están activadas,
  - solicitar el permiso Android 13+,
  - abrir directamente Ajustes > GAKS > Notificaciones.
- Solicitud automática una vez tras el primer inicio de sesión.
- Botones de notificaciones interceptados antes de la lógica web antigua.
- Prueba de aviso usa notificación local nativa.
- Centro de actualizaciones:
  - muestra versión instalada 1.0.16,
  - botón Buscar actualizaciones,
  - mensaje explícito si está actualizado/no hay versión publicada/error,
  - aviso automático si Supabase publica un version_code > 16,
  - acceso Actualizaciones en Más opciones.
- versionCode 16.
