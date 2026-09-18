# GAKS V40 — consolidación 2026-09-03

V40 parte de V39 y consolida las correcciones detectadas durante la auditoría de V38/V39.

## 1. Pendientes y Recursos
- **Más**, **Admin → Pendientes** y **Admin → Recursos** utilizan el mismo estado administrativo real.
- Se evita el caso en el que el perfil mostraba “Pendientes del administrador” pero al entrar a Admin parecía no haber tareas.
- Recursos se vuelve a contar al resolver, asociar o subir un demo.

## 2. Ejercicios y demostraciones
- Se incorpora `demo_family_id` para separar el nombre programado del ejercicio de la demostración reutilizable.
- Se incorpora tabla de familias de demostración y se migran los demos existentes a familias compartibles.
- Los 140 ejercicios que ya tenían video/imagen quedaron vinculados inicialmente a una familia de demo; además se enlazaron 12 variantes verificadas (banco/número/nombre equivalente) con sus familias correctas, dejando solo 12 demostraciones realmente faltantes en la rutina actual de Alex.
- Se usan `exercise_id`, `canonical_key`, alias y equivalencias conservadoras antes de declarar “Demostración pendiente”.
- Se ignoran para la búsqueda segura elementos normalmente no esenciales para el video: números de equipo, banco/banco ajustable, “si está disponible”, “si el equipo lo permite”, carga moderada, ligero, ajuste cómodo y rango controlado.
- Se conservan modificadores que sí pueden cambiar la técnica: inclinado/plano, unilateral/bilateral, dirección alta-a-baja/baja-a-alta, posición, agarre, etc.
- Si la equivalencia es única y segura, se reutiliza la demo. Si es dudosa, queda pendiente para decisión del administrador.
- Admin añade **Gestionar equivalencias**, con posibilidad de compartir una familia de demo y guardar alias permanentes.
- Antes de publicar una rutina, V40 audita los ejercicios y muestra reconocidos/con demo/sin demo.

## 3. Notificaciones duplicadas
- Se corrigió el doble origen de `RUTINA ACTUALIZADA`: el trigger de cambios directos ya no duplica el mensaje generado por una publicación versionada mediante RPC.
- La capa V40 del Admin no dispara un segundo push manual después de publicar; el mensaje insertado en backend activa el flujo FCM existente.

## 4. Dieta
- `CR`, `C` y `S` se traducen desde el renderer a **Crudo**, **Cocido** y **Servido/listo**.
- Se corrigió el JavaScript incrustado de **Guardar dieta en PDF**, que tenía una cadena multilínea inválida.
- La exportación PDF utiliza también los estados de pesado en texto completo.

## 5. Correcciones de arquitectura/legado
- V40 reemplaza la dependencia frágil entre scripts antiguos de Recursos que compartían estado entre IIFE distintos.
- El administrador V40 mantiene su propio estado de catálogo/recursos y se carga después de las capas anteriores para ser la implementación autoritativa.
- README y Firebase notes se actualizan a `versionCode 40 / versionName 1.0.40` y eliminan instrucciones obsoletas.
- Se alinean también todos los módulos de control de versión cargados en runtime, incluido `gaks-v37-authoritative.js`, para evitar que la app se identifique internamente como 1.0.39.

## Backend aplicado
- `gaks_demo_families` + RLS y políticas de administración/lectura.
- `gaks_exercises.demo_family_id`.
- RPCs admin para alias, compartir familia y asociar demo nuevo.
- `migym-resource-audit` actualizado para resolver por ID, alias, familia y equivalencia segura.

## Corrección final · demostraciones dentro del entrenamiento activo
- Se unifica el resolvedor de demos de las tarjetas de Entreno y del modo Entrenar.
- El modo Entrenar espera/rehidrata el catálogo dinámico antes de declarar una demostración como ausente.
- Se añaden reintentos breves tras autenticación, regreso a primer plano y evento `gaks:dynamic-catalog-ready`.
- El catálogo de ejercicios/familias/alias se conserva localmente durante 30 días para resolver demos inmediatamente tras abrir la app y soportar mejor el uso sin conexión.
- `Descargar rutina` espera a que el catálogo de demos esté listo antes de construir la lista de multimedia; las variantes que heredan una familia ahora también se incluyen en la descarga.
- Caso verificado que motivó el cambio: `Jalón al pecho #18` tiene demo disponible por la familia `Jalón al pecho`; no debe mostrar el falso mensaje “No hay demostración disponible”.

## V40 DEMOS FIX2 · entrenamiento activo
- El modo Entrenar precarga el catálogo antes de abrir la pantalla de series.
- El demo resuelto se guarda en una caché local independiente y también se recupera de la descarga offline de rutina.
- Entreno y Entrenar comparten el mismo resolvedor y la misma familia de demostración.
- Un MutationObserver evita que un fallback antiguo sobrescriba un video que sí existe con el mensaje falso “No hay demostración disponible”.
- La descarga de rutina registra las URL de los demos para que el modo Entrenar pueda resolverlas de inmediato, incluso al reabrir la app.
