# GAKS V24

Base: V23 estable.

Cambios aislados:
- Lista de compras: contraste del nombre corregido, cantidad destacada y estado secundario legible.
- Estados de pesado visibles: CR → Crudo, C → Cocido, S → Servido/listo.
- Traducción aplicada tanto en lista de compras como en detalle/explicación de dieta, sin modificar datos almacenados.
- Para Alex y Kelly, etiquetas principales de comidas normalizadas a: Desayuno, Snack, Pre entreno, Almuerzo, Cena.
- Kelly: limpieza visual de referencias a fútbol en dieta/inicio; Alex se conserva sin cambio.
- Se conserva el consumo de diet_update y routine_update ya generado por Supabase; la APK no crea eventos duplicados.
- Listener Android para push en primer plano con refresco interno y notificación local; segundo plano/cerrada queda a cargo de FCM/Android.
- Se conserva registro de token FCM, canal de alta importancia, POST_NOTIFICATIONS Android 13+ y vibración/sonido existentes.
- versionCode 24 / versionName 1.0.24.
