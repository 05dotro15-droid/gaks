# GAKS V28

- Corrige detección nativa del bridge: también reconoce `window.GaksAndroid` y plataforma Android.
- Firebase Messaging solicita token directamente desde `MainActivity` al arrancar, con segundo intento diferido.
- Logcat siempre emite `GAKS_FCM MAIN_ACTIVITY_READY` y `NATIVE_TOKEN_REQUEST_START`, permitiendo confirmar ejecución nativa.
- Token nativo se guarda temporalmente en localStorage y se entrega al bridge cuando está disponible.
- Registro Supabase reporta `app_version 1.0.28`.
- Mantiene correcciones previas: modal GAKS único, botón Atrás, dieta/compras y backend FCM.
