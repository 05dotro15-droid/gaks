# Arquitectura de videos

La carpeta `www/media/` se omite intencionalmente del paquete Capacitor para no convertir la APK en un archivo de ~90 MB.

Mientras los videos actuales sigan publicados con la web estable, las referencias locales de esta fuente apuntan a `https://gaksfit.com/media/...`. Los videos que el Admin sustituye en `migym-media-public` siguen teniendo prioridad.

Al tocar **Descargar rutina**, el contenedor nativo descarga solo los recursos usados por la rutina del usuario y los guarda en el directorio privado de GAKS. En reproducciones posteriores, el bridge resuelve automáticamente el archivo local antes de usar la URL remota.
