# GAKS Android V23

Corrección estructural sobre V22:

- Fuerza los recursos del APK y elimina el caché PWA antiguo al primer arranque de V23.
- Desactiva el Service Worker web dentro del APK Android.
- Acceso al administrador por `./admin/index.html`, sin depender de rutas absolutas.
- Atrás desde Administrador vuelve al perfil del usuario.
- Notificaciones usan permisos reales de Android/Capacitor.
- Aviso de activación se muestra mientras Android no haya concedido permiso.
- Selector de 5 sonidos y 5 vibraciones mediante botones oscuros (sin `<select>` blanco nativo).
- Prueba de vibración usa el puente Android y permiso `VIBRATE`.
- Canales nuevos V23 evitan reutilizar canales antiguos sin vibración.
- Actualizaciones muestran siempre estado de búsqueda, resultado o error.
- versionCode 23 / versionName 1.0.23.
