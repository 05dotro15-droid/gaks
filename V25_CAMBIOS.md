# GAKS V25

- Corrige registro persistente del token FCM y reintento después del inicio de sesión.
- Prepara recepción nativa de avisos de dieta y rutina con la app abierta, en segundo plano o cerrada.
- Backend automático enlaza `diet_update` y `routine_update` con FCM y deduplica eventos cercanos.
- Backend de nuevas versiones enlaza publicaciones activas de `gaks_app_releases` con FCM para dispositivos registrados.
- Elimina el `confirm()` gris heredado de actualización; queda solo el modal con diseño GAKS.
- Modal GAKS actualizado a versión instalada 1.0.25.
- Mantiene intactos los cambios de dieta/lista de compras de V24.
