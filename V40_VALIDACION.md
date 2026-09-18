# GAKS V40 — validación técnica

Fecha: 2026-09-03

## Código empaquetado
- JavaScript externo + scripts inline revisados con `node --check`: **123 scripts, 0 errores sintácticos**.
- `package.json`, `capacitor.config.json` y `google-services.json`: JSON válido.
- Referencias locales `<script src>` / `<link href>` en app y Admin: **0 archivos faltantes**.
- No quedan referencias runtime a `versionCode 39`, `BUILD=39` ni `1.0.39` en los archivos activos auditados.
- Build actual: **versionCode 40 / versionName 1.0.40**.

## Casos de equivalencia probados
- `Curl inclinado con mancuernas #36 + banco #38` = demo de `Curl inclinado con mancuernas`.
- `Apertura alta-a-baja en Functional Trainer #27` = demo de `Apertura alta-a-baja en poleas #27`.
- `Remo unilateral en polea ajustable #26` = demo de `Remo unilateral en polea #26`.
- `Press plano ...` ≠ `Press inclinado ...`.
- `Apertura alta-a-baja ...` ≠ `Apertura baja-a-alta ...`.

## Backend V40 aplicado
- Tabla `gaks_demo_families` con RLS.
- `gaks_exercises.demo_family_id` e índice.
- 87 familias de demostración actuales.
- 152 ejercicios vinculados a familia tras migración y equivalencias verificadas.
- 12 demostraciones de ejercicio realmente pendientes después de limpiar falsos positivos heredados.
- RPCs administrativos de alias/familia/demo: ejecución anónima revocada; cada RPC además valida `migym_is_admin()`.
- `migym-resource-audit` desplegado en versión 13, resolviendo por ID, alias, familia y equivalencia conservadora.
- Trigger de rutina corregido para no duplicar el mensaje generado por una publicación versionada.

## Correcciones V38/V39 incorporadas
- Pendientes coherentes entre Más/Admin/Recursos.
- Renderer V36/V39 de Recursos/Pendientes que competía con V40 eliminado del HTML activo.
- Exportación de dieta a PDF corregida.
- Estados Crudo/Cocido/Servido/listo corregidos desde render.
- Documentación Firebase/versiones saneada.

## Validación adicional · demo en modo Entrenar
- `Jalón al pecho #18` está marcado `available` en Supabase y pertenece a la familia `Jalón al pecho` con video masculino y femenino.
- Se añadió `gaks-v40-focus-demo-bridge.js` como último resolvedor del modo Entrenar.
- El catálogo dinámico ahora tiene caché local y método `ensure()`.
- La generación de la descarga offline espera la resolución del catálogo antes de enumerar demostraciones.

## Validación DEMOS FIX2
- Caso objetivo: Jalón al pecho #18, demo disponible por familia Jalón al pecho.
- Se añadió precarga antes de gaksStartFocusAt, caché local de demos, reutilización del descriptor offline y reparación de falsos negativos tardíos.
