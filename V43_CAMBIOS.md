# GAKS V43 · Fase 3 consolidada

Versión Android: **1.0.43.5**  
versionCode: **48**  
Versión de paquete: **43.5.0**

## Correcciones incorporadas
- **Usuarios** vuelve a mostrar tarjetas de perfil y al tocar una cuenta abre su **ficha completa**, no el chat.
- El listado nuevo deja fuera la etiqueta heredada de “nuevo usuario” y prioriza nombre, correo, plan y chats sin leer.
- La navegación lateral se fuerza de forma consistente: si hay un chat, ficha o detalle abierto, tocar **Pendientes / Usuarios / Recursos / Ejercicios / Dietas / Chat** cierra el detalle anterior y abre la sección elegida.
- El placeholder de búsqueda cambia según la sección activa.
- El chat privado de Admin recibe un pulido visual de cabecera, burbujas, etiquetas de rol y caja de respuesta.
- El chat del usuario también recibe un pulido visual: contenedor, selector de profesional, burbujas, contraste y compositor.
- Se conservan las correcciones de Fase 2: confirmación antes de salir de Admin, “nuevo usuario” fuera de Pendientes, botones responsivos y navegación Atrás por niveles.

## Fase 3 · Versionado profesional
- Una nueva rutina o dieta se crea primero como **BORRADOR**.
- Un borrador puede enviarse al usuario y pasa a **ENVIADA AL USUARIO**.
- La rutina/dieta que el usuario ya tiene permanece activa hasta que acepte la nueva versión.
- El usuario recibe push con el profesional correspondiente y ve **Ver cambios** en Entreno o Nutrición.
- **Ver cambios** muestra añadidos, modificados y retirados, además del motivo del cambio cuando se captura.
- Abrir o revisar la actualización no la da por atendida: mientras siga pendiente no se marca como leída por entrar al panel.
- Al pulsar **Aceptar cambios**, la versión pasa a **ACEPTADA** y entonces se vuelve activa.
- Admin puede cancelar un borrador o una versión enviada pendiente sin modificar el plan activo.
- La ficha Admin muestra historial de versiones y estados.
- Dieta conserva la lista de compras asociada a la versión.
- La aceptación de dieta suprime la notificación duplicada del trigger de sincronización; el aviso se emite al **enviar** la versión, no al aceptarla.
- El contador de versión toma en cuenta tanto el historial de revisiones como la versión activa en `migym_user_state` para evitar colisiones con datos previos.

## Backend
Migraciones ya aplicadas en Supabase:
- columnas de workflow en `migym_plan_revisions`;
- vínculo `plan_revision_id` en `migym_messages`;
- RPC Admin para crear/enviar/cancelar versiones;
- RPC de usuario para aceptar versiones;
- ajuste del contador de versiones;
- texto FCM específico para actualizaciones que requieren aceptación;
- reutilización del trigger FCM existente, sin crear una segunda ruta de push.

No es necesario ejecutar SQL manualmente para probar esta compilación.
