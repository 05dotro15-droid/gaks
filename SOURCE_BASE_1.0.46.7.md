# GAKS 1.0.46.7 · Source recovery

Base web: GAKS 1.0.46.5 funcional.

## Corrección de la rotura visual de 1.0.46.6
La 46.6 insertó la etiqueta del nuevo script usando el primer `</body>` encontrado en `index.html`. Ese archivo contiene cadenas HTML de impresión con `</body></html>` dentro de JavaScript. El navegador interpretó el `</script>` inyectado dentro de esa cadena como cierre real del script principal y mostró el resto del JavaScript como texto.

En 46.7 **no se busca ni reemplaza `</body>`**. El controlador final se carga como archivo externo anexado al EOF de `index.html`, igual que los hotfix ya estables.

## Pendientes tratados
- Atrás nativo durante Editar sesión: usa la rama nativa ya existente `#gaksV23Backdrop.show` como sentinel invisible y abre el modal real de edición cuando Android consume Atrás. No se modifica `classes.dex`.
- Notificaciones: cuando Android reporta notificaciones y superposición activas, elimina y oculta de forma persistente todos los prompts históricos conocidos.

VersionName: 1.0.46.7
VersionCode: 126
