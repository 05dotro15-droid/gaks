# GAKS Usuario 1.0.48.0 / code 139

Base: 1.0.47.9 SAFE / code 138 confirmada funcional por el usuario.

Cambio único de esta versión:
- Al aumentar el número de series durante el descanso final, la interfaz recalcula si realmente es la última serie usando el conteo vigente.
- Se sincroniza el estado de descanso persistido para que no reaparezca “Terminar ejercicio” cuando existe una serie adicional pendiente.

No se modifican Auth, background, offline, contador nativo, notificaciones, MainActivity ni DEX.
