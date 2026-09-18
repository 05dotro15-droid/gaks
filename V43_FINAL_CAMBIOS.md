# GAKS V43 FINAL — 2026-09-07

Versión Android: **1.0.43.5**  
versionCode: **48**  
Versión de paquete: **43.5.0**

## Corrección final
- Chats privados del usuario completamente separados por especialista:
  - Dr. Rendón → `target_role=doctor`
  - Nutrióloga Cetina → `target_role=nutritionist`
  - Coach Gómez → `target_role=coach`
- Un mensaje de un especialista ya no aparece en la conversación de otro.
- Avisos generales de GAKS se muestran aparte y no contaminan los chats de especialistas.
- Admin también separa las conversaciones por especialista.
- Desde Pendientes se abre directamente el especialista correcto.
- Dentro del chat Admin hay selector visual de Dr./Nutrióloga/Coach; cada pestaña consulta exclusivamente su `target_role`.
- Al responder desde Admin, el mensaje conserva el `target_role` del especialista activo.
- No se modificó el flujo de rutinas, dietas, versionado, recursos, ejercicios, PDF ni entrenamiento.

Esta compilación se considera **V43 FINAL**.
