# GAKS V34 · Cambios de prueba

## Temporizador
- Se elimina el contador flotante HTML antiguo como interfaz visible.
- Existe un solo overlay flotante nativo para cuando el usuario abandona la pantalla principal de descanso, tanto dentro de GAKS como sobre otras aplicaciones.
- Mientras la pantalla principal de descanso está visible, el overlay nativo se oculta.
- Al tocar el overlay se abre directamente la rutina/descanso activo.
- Arrastrar el overlay solo lo mueve y no abre la app.
- El diseño nativo se aproxima al flotante negro/dorado de GAKS, con +10 s y Cerrar.
- Al llegar a cero permanece como SEGUIR ENTRENANDO.

## Rutina activa / pausada
- Al iniciar un entrenamiento se conserva su posición exacta.
- Tocar Entreno durante una sesión activa lleva directamente a donde se dejó.
- Se agrega Guardar y continuar después debajo de Registrar serie y también durante descanso.
- Pausar no guarda la rutina como finalizada: conserva borradores, series, pesos, repeticiones y posición.
- Al volver a Entreno, una rutina pausada ofrece Continuar entrenamiento, Reiniciar rutina o Cancelar.
- Reiniciar elimina solo el progreso de esa sesión incompleta, no el historial anterior.
- Al guardar definitivamente la sesión se limpia el estado pendiente.

## Dieta
- El selector y el encabezado principal se fuerzan a usar el rango real de fechas del plan (por ejemplo, 31 Ago - 6 Sep), derivado de subtítulo/días.
- Se evita que la UI vuelva a mostrar Semana X cuando el plan contiene fechas.

## Versión
- versionCode 34
- versionName 1.0.34
- Esta versión es de prueba. No publicar en gaks_app_releases hasta validación física.
