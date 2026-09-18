# GAKS V37 — Corrección de navegación de rutina y overlay

- El deep link del overlay Android ahora llama a `gaksV37ResumeRest`, eliminando la referencia obsoleta a V35.
- Tocar el overlay, dentro o fuera de GAKS, reabre la rutina activa y el descanso principal.
- Mientras exista una rutina con estado `active`, tocar Entreno siempre vuelve a esa sesión, sin depender del día de la semana seleccionado.
- Las rutinas `paused` siguen siendo específicas por día: solo bloquean Entreno si corresponden al día calendario actual o al elegir ese día manualmente.
- Durante un descanso nativo, Siguiente/Anterior ejercicio se interceptan en cada toque, no solo al abandonar por primera vez el contador principal. El descanso nativo continúa y el overlay permanece visible.
- VersionCode 37 / VersionName 1.0.37.
