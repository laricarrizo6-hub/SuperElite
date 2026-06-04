# SuperEliteG2

Aplicación web para administrar personajes y su galería multimedia.

## Ejecutar con guardado automático en `characters.json`

Para que al agregar, editar o eliminar personajes desde la página también se actualice el archivo `characters.json`, abre el proyecto con el servidor incluido:

```bash
node server.js
```

Luego entra en:

```text
http://localhost:3000
```

El navegador por sí solo no puede escribir archivos locales. Por eso `server.js` expone el endpoint `/api/characters`, sirve la página y guarda automáticamente el listado actualizado en `characters.json`.

## Notas

- Los personajes se cargan desde `characters.json`.
- Las altas, ediciones y eliminaciones de personajes se persisten en `characters.json` cuando la app está corriendo con `node server.js`.
- La multimedia continúa guardándose en el almacenamiento local del navegador.

## Batallas y calificaciones

- La página **Batallas** carga el historial desde `Batallas.json` y lo combina con las batallas guardadas en el navegador.
- Cuando un personaje gana, también hereda automáticamente las victorias del personaje derrotado dentro de la misma etiqueta.
- Las calificaciones se calculan como porcentaje de victorias por etiqueta: `victorias / (victorias + derrotas) * 100`.
- Desde **Batallas** puedes descargar `calificaciones.txt` para copiar su contenido a `calificaciones.json`, descargar `Batallas.json` con el historial actualizado o cargar un `Batallas.json` anterior para no perder batallas ya disputadas.
