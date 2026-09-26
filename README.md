# Laboratorio 7 — Spark MLlib

Análisis exploratorio, segmentación con KMeans y modelado del salario mensual de personas asalariadas de la ENEIC (2025 para desarrollo, 2026T1 para prueba final), con Spark 3.5 y `pyspark.ml`.

**Integrantes:** Felipe Aguilar (23195) · Nicolás Concuá (23197)

## Contenido

- `lab7_analisis_segmentacion.ipynb`: notebook entregable (actividades 1 a 8).
- `outputs/`: figuras del modelado y del análisis de errores.
- `models/`: mejores pipelines de validación y modelos finales (se generan al ejecutar).

## Ejecución

1. Ejecutar `docker compose up --build`.
2. Abrir `http://localhost:8888` y ejecutar `lab7_analisis_segmentacion.ipynb` de principio a fin.

Si no existen, el notebook descarga las cinco bases de Personas del INE a `data/raw/`. Los conjuntos preparados de 2025 y 2026T1 se guardan en `data/processed/` en formato Parquet.

## Resultados en 2026T1

| Modelo | MAE (Q) | RMSE (Q) | R² |
|---|---|---|---|
| Referencia (media 2025) | 1,718 | 2,871 | −0.003 |
| Regresión lineal (sin regularización) | 1,241 | 2,164 | 0.431 |
| Random Forest (100 árboles, profundidad 20) | 1,080 | 1,938 | 0.543 |
