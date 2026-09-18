# GAKS V29 — FCM pull desde almacenamiento nativo

- Android conserva el token FCM en SharedPreferences.
- JavaScript consulta el token cuando el WebView y la sesión ya están listos.
- Se elimina la dependencia temporal de que el token sea empujado al WebView en el instante exacto.
- Reintento de guardado en Supabase hasta confirmar éxito.
- Logs GAKS_FCM: TOKEN_CACHED_NATIVE, TOKEN_READ_BY_WEBVIEW, NATIVE_CACHE_PULLED, SUPABASE_SAVE_OK/ERROR.
- versionCode 29 / versionName 1.0.29.
- Sin cambios de dieta, rutina o diseño.
