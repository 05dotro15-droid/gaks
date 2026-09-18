# Firebase / FCM en GAKS V41

La configuración cliente `google-services.json` corresponde a `com.gaksfit.app` y el proceso `npm run android:prepare` la copia a `android/app/google-services.json` cuando prepara Android.

## Estado actual

- Android: `versionCode 41` / `versionName 1.0.41`.
- Registro de dispositivo y recepción FCM están integrados en la aplicación.
- El envío de push se realiza desde el backend de GAKS mediante Supabase/Edge Functions.
- **Nunca** se debe incluir una cuenta de servicio, `service_role` ni otra credencial privada dentro del APK o del código web público.

Este archivo ya no marca como “pendiente” una credencial del servidor porque el backend de notificaciones está desplegado. Si se rotan credenciales de Firebase en el futuro, la actualización debe realizarse exclusivamente en los secretos del backend.
