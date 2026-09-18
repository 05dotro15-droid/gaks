# GAKS Android V21 — reconstrucción sobre V17 estable

Esta versión NO deriva de V18/V19/V20.

## Conservado sin modificar
- Inicio de sesión y persistencia de sesión de V17.
- Panel Administrador y detección de administrador.
- Rutinas, dieta, progreso, chat, hogar y navegación existente.
- Puente nativo de Capacitor/Android y flujo FCM de V17.

## Añadido de forma aislada
- Aviso visible en Inicio para activar notificaciones cuando el permiso no está concedido.
- Controles directos en Ajustes para 5 sonidos (3 largos, 1 corto, 1 intermedio).
- Controles directos en Ajustes para 5 vibraciones, todas largas.
- Botones de prueba de sonido y vibración.
- Accesos directos desde Más a Notificaciones y alertas y Actualizaciones.
- Actualizaciones conserva el comprobador estable de V17 y muestra versión 1.0.21.
- El script de preparación fija versionCode 21 / versionName 1.0.21.

## Diseño de seguridad
No se reemplaza switchPanel, no se interceptan clics globales en captura y no se modifica la autenticación/admin.
