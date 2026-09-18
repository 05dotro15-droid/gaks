# GAKS V36 — corrección focalizada

- Overlay persistente al enviar GAKS a segundo plano: el estado de pantalla de descanso solo se considera visible si la WebView está realmente visible.
- Se retiran las capas autoritativas V34/V35 del arranque y se carga únicamente V36 para evitar interceptores antiguos.
- Rutinas incompletas: una sesión pausada solo intercepta Entreno si pertenece al día actual y a la fecha calendario actual; otros días solo muestran aviso al seleccionarlos manualmente.
- Notificaciones: la hoja nativa visible incluye permanentemente “Contador sobre otras apps” con estado Activado/Desactivado y acceso al permiso Android.
- VersionCode 36 / versionName 1.0.36.
