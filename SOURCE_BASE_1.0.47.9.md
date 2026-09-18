# GAKS 1.0.47.9 · code 138

Base exacta: GAKS 1.0.47.7 / code 136 confirmada por el usuario como última versión funcional.

Cambios exclusivos de esta compilación:
1. Al terminar un ejercicio, el avance automático abre el primer ejercicio NO HECHO en el orden original de la rutina. Si se saltó el 2 para hacer el 3, al terminar 3 vuelve al 2; al terminar 2 continúa al siguiente pendiente.
2. Canonización visual de `Fondos asistidos #25` y `Fondos asistidos en Chin/Dip #3` a `Fondos asistidos en máquina`, incluyendo progreso/historial sin reescribir IDs ni perder registros.
3. Lista de compras: fuera de Modo Súper no se modifica el estado. En Modo Súper se muestran pendientes y comprados; tocar un comprado lo devuelve a pendiente.

No se modificaron Auth, lifecycle/background, offline, notificaciones, contador flotante, MainActivity.java, GaksRestService.java, DEX ni lógica nativa.
