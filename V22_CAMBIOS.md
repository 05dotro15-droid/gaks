# GAKS Android V22

Corrección aislada sobre la base V21/V17 estable, sin modificar la lógica de acceso al panel administrador.

- Menú de Notificaciones abre en un panel independiente y no depende de tarjetas ocultas del Perfil.
- Permiso de notificaciones consultado directamente con Android.
- Mensaje de activación en Inicio mientras Android no tenga el permiso.
- 5 sonidos y 5 vibraciones largas con selectores oscuros y legibles.
- Prueba de vibración usa el Vibrator nativo de Android.
- Aviso completo usa una notificación nativa configurada con el sonido y vibración elegidos.
- Menú de Actualizaciones abre en un panel independiente y siempre muestra resultado o error.
- Botón Atrás dentro de /admin/ regresa al perfil de usuario en lugar de iniciar el flujo de salida.
- versionCode 22 / versionName 1.0.22.
