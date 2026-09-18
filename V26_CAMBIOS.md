# GAKS V26

- Registro FCM reforzado: Android obtiene el token directamente desde Firebase Messaging y lo entrega al bridge web para guardarlo en `gaks_fcm_devices`.
- Se conserva el listener de Capacitor como respaldo y se reintenta sincronización tras autenticación.
- El botón/gesto Atrás de Android cierra la hoja de Notificaciones/Actualizaciones y vuelve a la pantalla anterior, igual que la X.
- Sin cambios en dietas, rutinas, compras ni datos.
- versionCode 26 / versionName 1.0.26.


## Corrección de compilación
- Se añade explícitamente `com.google.firebase:firebase-messaging:25.0.1` al módulo app durante `android:prepare`, requerido porque `MainActivity` usa `FirebaseMessaging` directamente.
