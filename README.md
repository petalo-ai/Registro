# 勉強 · Tiempos de estudio

App personal para registrar tiempos de estudio diario de japonés y detectar patrones. Un solo archivo HTML, sin dependencias ni build.

## Qué hace

- Registro de sesiones por categoría: Kanji 漢字, Vocabulario 語彙, Podcast 聴解, Gramática 文法, Lectura 読解 y Otro
- Gráfico de barras apiladas por día (7 / 14 / 30 días)
- Patrón semanal: promedio de minutos por día de la semana
- Vista anual: heatmap tipo calendario de contribuciones (últimos 12 meses) con total, días activos y promedio
- Totales por mes (últimos 12 meses)
- Racha de días seguidos y distribución por categoría
- Exportar / importar respaldo en JSON (la importación fusiona sin duplicar)

## Datos y privacidad

Todos los registros se guardan en `localStorage` del navegador, en el dispositivo. Nada se envía a ningún servidor; GitHub Pages solo sirve el código.

Implicaciones:
- Los datos son por navegador y por dispositivo (no se sincronizan solos)
- Se pierden si limpias los datos de navegación → exporta un respaldo JSON de vez en cuando
- Para pasar datos entre dispositivos: exportar en uno, importar en el otro

## Estructura de datos

Clave de localStorage: `registro-estudio-jp`

```json
{
  "entries": [
    { "id": "1722800000000-a1b2", "date": "2026-08-04", "cat": "kanji", "min": 30 }
  ]
}
```

## Uso

Abrir `index.html` en cualquier navegador, o visitar la página publicada con GitHub Pages. En el teléfono: "Agregar a pantalla de inicio" para usarla como app.

## Stack

HTML + CSS + JavaScript vanilla en un solo archivo. Los gráficos están hechos con CSS (sin librerías), así que funciona incluso sin conexión una vez cargada. Única dependencia externa: la fuente Shippori Mincho de Google Fonts (con fallback a fuentes del sistema).
