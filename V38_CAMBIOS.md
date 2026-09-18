# GAKS V38 — corrección de versión instalada

- Corrige la desincronización detectada en V37: Android tenía versionCode 37, pero archivos web internos eran reescritos por `android:prepare` como 1.0.35.
- Unifica la versión mostrada y comparada por la app en 1.0.38 / build 38.
- Actualiza los comprobadores de versión activos (`gaks-v16-patches.js`, `gaks-v17-patches.js`, `gaks-v24-native-controls.js`) y la capa autoritativa actual.
- `prepare-android.mjs` ahora genera versionCode 38 / versionName 1.0.38 y ya no vuelve a forzar 1.0.35.
- No modifica la lógica estable de navegación/overlay de V37.

## Ajustes finales de notificaciones y dieta
- Se elimina el diálogo gris duplicado de notificaciones.
- Tras conceder el permiso, la tarjeta de activación se oculta al detectar el estado concedido.
- Se muestra durante 2 segundos el mensaje `✓ Notificaciones activadas`.
- Dieta mantiene el rango de fechas en el selector superior y usa `Plan de alimentación · Semana N` en el encabezado blanco.

## Navegación durante descanso y ejercicios pendientes
- No se crea ningún temporizador adicional: se reutiliza exclusivamente el mismo servicio/overlay nativo existente.
- Si el descanso sigue activo y el usuario intenta ir a otra serie, terminar el ejercicio, ir al ejercicio siguiente o al anterior, se pregunta si desea `Continuar con contador flotante` u `Omitir descanso`.
- `Continuar con contador flotante` conserva el mismo `endAt` nativo y oculta únicamente la vista principal del descanso para que aparezca el overlay existente.
- `Omitir descanso` cancela solamente el descanso actual antes de continuar.
- El botón final del ejercicio durante descanso se presenta como `Terminar ejercicio`.
- `Siguiente ejercicio` busca el siguiente ejercicio pendiente y puede volver a uno saltado anteriormente; los ejercicios ya completados se omiten.
- Al terminar un ejercicio y registrar su RIR final, el flujo también vuelve al primer ejercicio pendiente en vez de avanzar ciegamente por índice.

## Consolidación final 2026-09-03 · Nutrición + flujo de edición
- Nutrición: botón «Solicitar ajuste de dieta» movido al encabezado, sustituyendo la leyenda «Perfil de dieta».
- Encabezado de semana: muestra solo rango de fechas y usa nombres completos de meses cuando están disponibles.
- El subtítulo repetitivo de fecha/perfil se elimina; «Estado de pesado: Crudo · Cocido · Servido/listo» se coloca inmediatamente bajo «Plan de alimentación · Semana N».
- En detalle de comida se oculta Lista de compras y se añade botón contextual «Preparación · <tipo>». Lee campos preparation/preparacion/instructions/instrucciones/notes sin inventar contenido si no existe.
- Modo Súper: los productos no cambian de estado mientras está desactivado. Al activarlo se muestra explicación y confirmación en modal oscuro; solo activo permite marcar/desmarcar compras.
- Lista de compras: contraste oscuro coherente con GAKS.
- Descanso: aceptar una vez el contador flotante se conserva para todo ese descanso; no vuelve a preguntar al navegar hasta que comience un descanso nuevo.
- RIR: si la serie ya tiene RIR guardado, continuar con el contador flotante no vuelve a pedirlo.
- Edición de ejercicio completado: editar una serie intermedia continúa a la siguiente serie del mismo ejercicio; solo tras la última vuelve al flujo de siguiente ejercicio pendiente.
- Se mantiene un único temporizador/overlay nativo y build/version 38 / 1.0.38.
