# GAKS V32 · Verificación antes de compilar

Versión de desarrollo: **1.0.32** · Android versionCode **32**.

## Cambios integrados
- Catálogo dinámico de demos resuelto desde el núcleo del visor de ejercicios, no solo mediante un parche posterior.
- Capa V32 autoritativa cargada después del catálogo V31.
- Separación de referencias históricas y datos actuales: las repeticiones de una sesión previa ya no se cargan como si fueran series realizadas en la sesión actual.
- Contexto de borradores separado por semana para evitar arrastrar estado completado de semanas anteriores.
- Reanudación de la sesión activa en el ejercicio/posición guardados.
- Conservación de series extra al repetir una rutina y controles de aumento/reducción de series.
- Guardar/modificar una serie anterior vuelve a iniciar el descanso.
- Temporizador Android nativo mediante foreground service.
- Overlay opcional sobre otras aplicaciones con permiso SYSTEM_ALERT_WINDOW.
- Al terminar el descanso, el servicio mantiene el estado “SEGUIR ENTRENANDO” hasta volver a la rutina o cerrarlo manualmente.
- Sonido y vibración nativos al finalizar el descanso, con solicitud de audio focus transitorio con ducking.
- Notificación de fin de descanso independiente de la WebView.
- Servicio Firebase nativo para recibir mensajes de datos de alta prioridad y reproducir el aviso solicitando audio focus.
- Fuente de `gaks-fcm-send` preparada para FCM data-only de alta prioridad. **No desplegar esta Edge Function antes de que V32 esté instalada**, porque V31 depende del flujo anterior.
- Etiqueta de dieta preparada para usar el rango de fechas del plan.
- Admin: filtro final para no mostrar como “faltantes” ejercicios que sí tienen demo en `gaks_exercises`, y conteo del catálogo dinámico.

## Verificaciones estáticas realizadas
- `node --check` correcto en `gaks-v32-authoritative.js`.
- `node --check` correcto en `gaks-v31-dynamic-catalog.js`.
- `node --check` correcto en `scripts/prepare-android.mjs`.
- Sintaxis del bloque V32 de Admin comprobada.
- `prepare-android.mjs` ejecutado sobre un esqueleto Android temporal y comprobado que genera:
  - versionCode 32 / versionName 1.0.32;
  - permisos de notificaciones, vibración, overlay, wake lock y foreground service;
  - `GaksRestService`;
  - `GaksFirebaseMessagingService`;
  - bridge nativo en `MainActivity`.
- Confirmado que `gaks-v32-authoritative.js` se carga después de `gaks-v31-dynamic-catalog.js`.
- Confirmado que los controles de versión cargados (v16/v17/v24) quedan alineados a 1.0.32.
- Confirmado que la lógica web evita duplicar sonido/vibración cuando el servicio nativo V32 controla el descanso.

## Pruebas obligatorias en teléfono antes de publicar
Estas funciones dependen de Android/OEM y no pueden darse por verificadas únicamente con inspección del código:
1. Compilar en Android Studio con las dependencias reales de Capacitor/Firebase.
2. Instalar sobre V31 usando la misma firma.
3. Con Spotify reproduciendo música, iniciar un descanso y comprobar que el aviso de GAKS provoca ducking temporal.
4. Probar fin de descanso con GAKS en segundo plano y con pantalla bloqueada.
5. Activar “Mostrar sobre otras apps” y comprobar contador móvil, X y estado “SEGUIR ENTRENANDO”.
6. Tocar el contador/notificación y verificar que vuelve al ejercicio/serie correcto.
7. Probar notificación FCM con app en segundo plano/bloqueada **después** de desplegar la nueva fuente de `gaks-fcm-send` en un entorno de prueba o al momento de publicar V32.
8. Entrenar una rutina de semana nueva y confirmar que ninguna serie de la semana previa aparece marcada como hecha.
9. Repetir una rutina ya guardada, agregar una serie extra y verificar que se registra.
10. Modificar una serie anterior y verificar que al guardar inicia descanso.
11. Probar los seis demos que V31 mostraba como ausentes.
12. Revisar Admin: recursos faltantes, conteo de biblioteca y badge de usuarios.

**Importante:** este paquete es fuente de prueba. No modifica `gaks_app_releases`, no publica APK y no dispara notificaciones de actualización.
