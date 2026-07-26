# Infraestructura de Datos Espaciales · Municipio de Libres, Puebla

Aplicación web para la consulta, filtrado y descarga de información geográfica del municipio de Libres, Puebla, consumiendo servicios OGC (WMS/WFS/WCS) publicados en GeoServer.

## Objetivo

Proporcionar un catálogo geoespacial interactivo que permita explorar capas de información (rezago social, unidades económicas, red vial, vulnerabilidad acuífera y modelo de elevación), filtrarlas por tipo de dato y palabras clave, y descargar los datos desde GeoServer.

## Funcionalidades principales

- Listado de capas geoespaciales con:
  - Miniatura, título, descripción, autor, fecha y tipo de dato (puntual, lineal, poligonal, raster).
- Buscador por palabra clave (rezago, economía, movilidad, vulnerabilidad, etc.).
- Filtros por tipo de dato:
  - Puntual, Línea, Poligonal, Raster.
- Menú desplegable en la barra de navegación para filtrar rápidamente por tema (rezago, DENUE, calles, vulnerabilidad, CEM).
- Botones por capa para:
  - Descargar datos (WFS/WCS desde GeoServer).
  - Descargar metadatos en formato JSON (generados dinámicamente en el navegador).
- Página informativa adicional con listado de capas, tipo y breve descripción.

## Arquitectura y tecnologías

- **Frontend:** HTML, CSS, JavaScript (Vanilla JS).
- **Framework de estilos:** Bulma + estilos personalizados para tarjetas, buscador y filtros.
- **Catálogo de contenido:** Archivo con metadatos de cada capa (thumbnail, título, autor, descripción, fecha, tipo, keywords).
- **Servicios geoespaciales:** GeoServer (WMS/WFS/WCS) sobre el workspace `libres` (rezago, denue, calles, libres, vulnerabilidad, dem).

> Nota: este repositorio incluye solo el frontend. GeoServer y la base de datos subyacente deben estar configurados aparte.

## Uso

1. Usa la barra de búsqueda para filtrar capas por palabras clave (ej. *movilidad*, *economía*, *vulnerabilidad*).
2. Utiliza los botones de filtro para ver solo capas puntuales, lineales, poligonales o raster.
3. Desde el menú “Información Geográfica” en la barra superior, selecciona un tema (Rezago, DENUE, Calles, Libres, Vulnerabilidad, CEM) para llenar automáticamente el buscador.
4. En cada tarjeta:
   - Haz clic en **Descargar** para obtener el SHP o GeoTIFF desde GeoServer.
   - Haz clic en **Metadatos** para descargar un archivo JSON con los metadatos de esa capa.[file:6]

## Créditos y datos

- Desarrollo: Brenda Soto Rivera.
- Fuentes de datos:
  - Indicadores de rezago social: CONAPO.
  - DENUE y capas base: INEGI.
  - Red vial: SCT.
  - CEM y vulnerabilidad acuífera: INEGI.
