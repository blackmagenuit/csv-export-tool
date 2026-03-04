# CSV Export Tool - Mining Reports

Herramienta para procesar reportes de minería desde archivos CSV y generar reportes en Excel con cálculos de ganancias en BTC y USD.

## Características

- ✅ Lectura inteligente de CSV (detección automática de encoding y separadores)
- ✅ Identificación automática de columnas de fecha e ingresos
- ✅ Filtrado por mes y año
- ✅ Cálculo automático de USD basado en precio BTC
- ✅ Generación de reportes Excel con formato
- ✅ Organización automática de archivos procesados
- ✅ Validación de días completos del mes

## Requisitos

- Python 3.8+
- Dependencias: `pandas`, `openpyxl`, `chardet`

## Instalación

```bash
pip install -r requirements.txt
```

## Estructura de carpetas

```
csv_tool/
├── input_csvs/          # Coloca aquí los archivos CSV
├── output/              # Reportes Excel generados
├── processed/           # CSVs después de procesarlos
├── csv_export.py        # Script principal
└── requirements.txt
```

## Uso

```bash
python csv_export.py
```

### Pasos:
1. Ingresa el año (ej: 2026)
2. Ingresa el mes (1-12)
3. Ingresa el precio BTC → USD
4. Ingresa la subcuenta (nombre del mining pool/wallet)
5. El script generará un Excel en `output/<subcuenta>/`

## Salida

El Excel generado incluye:
- **Subcuenta**: Nombre de la subcuenta
- **Description**: Tipo de ingreso (Miner Revenue)
- **Date**: Fecha de la transacción
- **Amount (BTC)**: Cantidad en Bitcoin
- **BTC Price**: Precio del BTC usado
- **USD**: Equivalente en USD
- **Totales**: Sumas automáticas
- **Hoja Control**: Validación de días del mes

## Autor

Blockware S.A
