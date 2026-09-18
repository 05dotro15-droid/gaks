# GAKS V42 · Correcciones post-prueba V41

Versión Android: **1.0.42** · `versionCode 42`

1. **Confirmaciones de rutina**
   - Se elimina el `confirm()` gris de Android del flujo de rutina ya trabajada.
   - Al tocar Iniciar rutina / Entrenar sobre una sesión ya realizada se usa un modal GAKS con Cancelar, Repetir rutina y Editar sesión.
   - No se muestra este modal por entrar simplemente a Entreno.

2. **Entreno no se abre solo**
   - El estado persistente V37 ya no reabre Modo entrenamiento si la sesión del día ya fue completada y no existe trabajo realmente incompleto por reanudar.
   - Un borrador auténticamente incompleto sí conserva la reanudación automática.

3. **Nombre del perfil en Nutrición**
   - Se neutraliza el ocultamiento heredado de V38.
   - Se restaura el subtítulo del plan y el nombre/perfil después de cada render.

4. **Badge rojo dentro de Admin**
   - V41 referenciaba un archivo que no quedó incluido en el ZIP.
   - V42 incluye el archivo real y calcula el total consolidado de personalizaciones, recursos, mensajes y nuevos usuarios.

5. **Se conservan las correcciones V40/V41**
   - demos, familias/equivalencias, PDF nativo, fondo blanco del PDF, cierre de último ejercicio, último descanso y contraste del resumen.
