# GAKS V17
Base: V16 corregida.

- Prueba de notificación con fallback 100% nativo en MainActivity (sin depender de LocalNotifications).
- Canales Android creados de forma nativa:
  - gaks_updates (coincide con el canal usado por gaks-fcm-send)
  - gaks_rest_native_v17
- Vibración reforzada y sonido gaks_alert.wav.
- Registro FCM persistente: guarda token localmente y reintenta sincronizarlo con gaks_fcm_devices tras el login.
- Centro de actualizaciones insertado de forma estática en Ajustes.
- Buscar actualizaciones siempre muestra un resultado al usuario.
- Comprobación automática al abrir.
- versionCode 17.
