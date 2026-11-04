# Constructor de polígonos por coordenadas

Página web de un solo archivo (sin servidor ni instalación) para capturar los vértices de un polígono en un cuadro de construcción y descargarlo en **KML**, **KMZ** o **Shapefile (SHP)**.

## Funciones

- Cuadro de construcción de vértices (agregar, quitar, limpiar, pegar lista).
- Coordenadas geográficas (decimales o grados/minutos/segundos) o UTM WGS84 (zona y hemisferio).
- Carga de archivos **CSV** exportados de Excel (coma, punto y coma o tabulador; con o sin encabezado `lat, lon` / `este, norte`).
- Cierre automático del polígono, vista previa, área (m²) y perímetro (m).
- Descargas: `.kml`, `.kmz` y `.zip` con `.shp`, `.shx`, `.dbf` y `.prj` (WGS84, EPSG:4326).

Todo se procesa en el navegador: ningún dato sale de tu equipo.

## Formato del CSV

Ver `ejemplo.csv`. Dos columnas por vértice, una fila por vértice:

```csv
lat,lon
24.1450,-110.3200
24.1450,-110.3120
24.1390,-110.3120
24.1390,-110.3200
```

Para UTM usa los encabezados `este,norte` y revisa la zona y el hemisferio en la página (por defecto 12N).

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub y sube estos archivos a la raíz.
2. Ve a **Settings → Pages**.
3. En **Build and deployment**, elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`.
4. Guarda. En un par de minutos la página queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

También puedes abrir `index.html` directamente en el navegador.

## Dependencias

- [JSZip 3.10.1](https://stuk.github.io/jszip/) (cargado desde cdnjs) para generar KMZ y el zip del SHP.

## Notas

- El área y el perímetro se calculan proyectando a UTM (zona del centroide, o la indicada en modo UTM).
- El anillo se orienta en sentido antihorario para KML y horario para SHP.
- No valida auto-intersecciones del polígono.

## Licencia

MIT
