# GAKS Capacitor Android · V43 Fase 3 consolidada

Base: V43 Fase 2, consolidada con las correcciones de navegación/Usuarios y el flujo profesional de versiones de rutina y dieta.

- package version: `43.5.0`
- Android versionCode: `47`
- Android versionName: `1.0.43.5`
- package id: `com.gaksfit.app`

## Incluye
- Admin: Pendientes, Usuarios, Recursos, Ejercicios, Dietas y Chat.
- Usuarios vuelve a abrir la ficha completa, no el chat.
- Cambio de sección desde cualquier chat/detalle fuerza correctamente la pestaña elegida.
- Chat Admin visualmente refinado.
- Chat profesional: Comunidad + Dr. Rendón + Nutrióloga Cetina + Coach Gómez + Aviso general.
- Rutina/Dieta: BORRADOR → ENVIADA AL USUARIO → ACEPTADA, con cancelación de pendientes.
- El plan activo no cambia hasta que el usuario acepta.
- El usuario ve “Ver cambios” en Entreno/Nutrición y puede aceptar después de revisar el resumen.
- Historial de versiones y estados dentro de la ficha Admin.

## Android
Desde la carpeta descomprimida:

```powershell
npm install
npm run android:add
npm run android:prepare
npm run android:open
```

Firmar con el mismo keystore/alias usado en las versiones anteriores.


## V43 FINAL — chats separados por especialista
La compilación final 1.0.43.5 / versionCode 48 separa completamente los chats privados de Dr. Rendón, Nutrióloga Cetina y Coach Gómez, tanto para usuarios como para Admin. Ver `V43_FINAL_CAMBIOS.md`.
