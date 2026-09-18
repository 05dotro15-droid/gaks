# Validación V43 · Fase 3

- `package.json`: **43.5.0**.
- Android preparado para **versionCode 48 / versionName 1.0.43.5**.
- Constantes autoritativas de versión sincronizadas a 48 / 1.0.43.5.
- Migraciones Fase 3 aplicadas correctamente a Supabase.
- Columnas de workflow verificadas en `migym_plan_revisions`.
- `plan_revision_id` verificado en `migym_messages`.
- RPC de borrador/envío/cancelación/aceptación verificados como existentes.
- Flujo de push reutiliza `gaks_messages_fcm_dispatch` y `gaks_dispatch_message_fcm`.
- JS/MJS externos: validación de sintaxis con Node.
- Scripts inline de `www/index.html` y `www/admin/index.html`: validación de sintaxis con Node.
- Referencias locales estáticas de scripts/estilos/imágenes: verificadas.
- No se incluye `android/` ni `node_modules/` en el ZIP de fuente.
- ZIP final: prueba de integridad posterior al empaquetado.

## Pruebas manuales prioritarias
1. Admin → Usuarios → tocar usuario → abre ficha completa.
2. Con un chat/detalle abierto → tocar otra opción lateral → cambia de sección correctamente.
3. Revisar estética y funcionamiento de Chat, tanto en Admin como en usuario.
4. Crear borrador de rutina → comprobar que el usuario conserva la rutina activa.
5. Enviar borrador → usuario recibe aviso y aparece **Ver cambios**.
6. Entrar a Entreno sin aceptar → el pendiente debe permanecer.
7. Aceptar → nueva rutina se vuelve activa y el pendiente desaparece.
8. Repetir con dieta y verificar semana/lista de compras.
9. Cancelar una versión enviada → deja de aparecer como cambio pendiente sin alterar el plan activo.
