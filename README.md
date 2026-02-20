# Dashboard de Produccion de Paletizado

Dashboard interactivo en tiempo real para monitorear la produccion de paletizado, conectado directamente a Google Sheets.

**[Ver Dashboard en vivo](https://leonelmitechnologies-coder.github.io/dashboard-paletizado/)**

## Caracteristicas

- **Datos en tiempo real** — Conexion directa a Google Sheets con auto-refresh cada 60 segundos
- **5 KPIs principales** — Total Pallets, Cantidad Total, Promedio/Dia, Pallets Enviados Hoy, Productos Enviados Hoy
- **Indicadores de mejora** — Porcentaje comparativo vs dia anterior, filtrado por turno
- **4 Graficos interactivos**:
  - Distribucion por Destino (Doughnut)
  - Distribucion por Condicion (Barras verticales)
  - Pallets por Fecha con linea de tendencia (Linea)
  - Cantidad por Destino (Barras horizontales)
- **Filtros avanzados** — Fecha (calendario), Destino, Condicion, Turno + boton Limpiar filtros
- **Tabla de detalle** — Ultimos 10 pallets con opcion de expandir a todos
- **Responsive** — Adaptable a escritorio, tablet y movil

## Stack Tecnico

- HTML5 / CSS3 / JavaScript (Vanilla)
- [Chart.js 4.4.0](https://www.chartjs.org/) + chartjs-plugin-datalabels
- [Flatpickr](https://flatpickr.js.org/) (selector de fechas, locale espanol)
- [Google Fonts - Inter](https://fonts.google.com/specimen/Inter)
- Datos via [opensheet.elk.sh](https://opensheet.elk.sh/) + Google Visualization API (fallback)

## Arquitectura

```
Google Sheets (fuente de datos)
        |
        ├── opensheet.elk.sh (metodo primario - JSON completo)
        └── Google Visualization API / JSONP (fallback)
                |
        Dashboard (single-file HTML)
                |
                ├── KPIs en tiempo real
                ├── Graficos Chart.js
                ├── Filtros interactivos
                └── Tabla de detalle
```

## Uso

Abrir directamente en el navegador:
- **Online**: [https://leonelmitechnologies-coder.github.io/dashboard-paletizado/](https://leonelmitechnologies-coder.github.io/dashboard-paletizado/)
- **Local**: Abrir `dashboard-paletizado.html` como archivo en el navegador

No requiere instalacion, servidor ni dependencias locales.

## Licencia

MIT
