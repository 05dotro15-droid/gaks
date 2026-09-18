# GAKS V41 · Correcciones consolidadas

Versión Android: **1.0.41** · `versionCode 41`

## Correcciones de esta revisión

1. **Dieta → Guardar en PDF**
   - Android usa impresión nativa mediante `PrintManager` en lugar de abrir una pestaña WebView.
   - El sistema muestra la opción nativa **Guardar como PDF** y, al salir, vuelve a GAKS.
   - El documento se genera con **fondo blanco**, texto negro, bordes visibles y dorado GAKS de alto contraste.

2. **Rutina reanudada / último ejercicio**
   - Si el último ejercicio ya tiene todas las series y RIR, aparece un botón inferior **Finalizar rutina →**.

3. **Admin → Pendientes**
   - El badge rojo interno usa el total consolidado (personalizaciones + recursos + mensajes + nuevos usuarios) y ya no es sobrescrito por el renderer anterior.

4. **Saltar último descanso**
   - Al omitir el descanso del último ejercicio, si la rutina está completa se abre el flujo de cierre y resumen.

5. **Resumen de sesión**
   - Contraste reforzado: títulos blancos, notas claras, métricas sobre tarjetas claras y acciones GAKS legibles.

6. **Rutina ya completada**
   - Se elimina el `confirm()` nativo.
   - El aviso sólo se muestra al tocar **Iniciar rutina**.
   - La confirmación usa un modal GAKS y permite iniciar una segunda sesión sin borrar la anterior.
   - Un borrador en curso se reanuda directamente.
