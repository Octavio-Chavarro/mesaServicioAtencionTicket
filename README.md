# Mesa Clara

Aplicación web estática para analizar exportaciones CSV de tickets GLPI. Permite filtrar por fechas de apertura o solución, ver indicadores globales, tiempos promedio, carga por técnico y casos pendientes, y exportar un reporte CSV.

## GitHub Pages

El workflow `.github/workflows/pages.yml` publica automáticamente la aplicación en GitHub Pages cuando se actualiza la rama `main` (también puede ejecutarse manualmente desde Actions). Para habilitarlo en el repositorio, ve a **Settings → Pages** y selecciona **GitHub Actions** como fuente. Después de fusionar este PR, la URL aparecerá en la ejecución del workflow o en esa sección de Pages.

## Uso local

Ejecuta `python3 -m http.server 4173 --bind 0.0.0.0` desde la raíz y abre la página. Selecciona el CSV exportado desde GLPI (delimitado por punto y coma); el procesamiento ocurre localmente en el navegador. No se envían los datos a un servidor. El reporte se descarga como `reporte-mesa-clara.csv`.

Se requieren las columnas `ID` y `Fecha de Apertura`. Se reconocen también `Título`, `Estado`, `Asignado a: - Técnico`, `Descripción` y `Fecha de solución`.
