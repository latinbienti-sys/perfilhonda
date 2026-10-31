# Perfil Honda — Tablero de Ventas (LatinBienMotors · Honda Mérida)

Tablero de unidades **facturadas y entregadas** con el perfil combinado del comprador.

➡️ **Ver el tablero:** [`reporte/tablero_ventas.html`](reporte/tablero_ventas.html)

## Contenido del tablero (una sola vista "Facturación")
- **KPIs:** 59 unidades facturadas · $1,891,076.96 (sin IVA) · 54 entregadas ($1,728,443.01)
- **Forma de venta (de las 54 entregadas):** 19 Contado · 35 Crédito SAV
- **Facturado por mes** (barras; corte 2026-10-30)
- **Perfil combinado del comprador (59):** 35 Caballeros + 24 Damas · rango de edad · departamento · actividad · profesión
- 3 Reservadas (almacén Reservas) · 4 Facturadas no entregadas (FNE)

## Archivos
| Archivo | Descripción |
|---|---|
| `reporte/tablero_ventas.html` | Tablero (una sola vista de Facturación) |
| `reporte/Reporte_Ventas_LatinBienMotors_2026.xlsx` | Reporte en Excel |
| `generar_tablero.js` | Generador del tablero HTML a partir de los datos |
| `datos/reporte_ventas_2026-10-30.json` | Datos del tablero (facturación, entregadas, perfil) |
| `reporte_motors.js` | Extractor de datos de Odoo (solo lectura; requiere credenciales locales) |

## Regeneración
```bash
node reporte_motors.js 2026          # extrae datos de Odoo (solo lectura)
uv run python generar_excel_reporte.py
node generar_tablero.js
```

⚠️ Solo se consulta la instancia **latinbienmotors.com** (BD `latinbien`) con acceso de solo lectura. Las credenciales se leen de un archivo local del equipo; nunca van en el repositorio.
