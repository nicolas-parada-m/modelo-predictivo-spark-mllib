<div align="center">

# 📊 Modelo Predictivo de Riesgo en Transacciones
### Apache Spark MLlib

`Python` · `PySpark` · `MLlib` · `Machine Learning`

</div>

---

## Contexto

El área de operaciones necesita **anticipar transacciones anómalas** dentro de un dataset de ventas simuladas (errores de stock, montos atípicos, horarios inusuales). Este proyecto consolida el trabajo de limpieza y transformación de datos hecho con RDDs en unidades anteriores, llevándolo hasta un **modelo de Machine Learning entrenado y evaluado** sobre el entorno distribuido de PySpark.

---

## Metodología

| Etapa | Detalle |
|---|---|
| **Limpieza y transformación** | Procesamiento con RDDs, manejo de fechas corruptas y recuperación de valores faltantes (precio, monto, cantidad) mediante lógica de negocio |
| **Preparación del dataset** | Columna `label` binaria (1 = riesgosa, 0 = normal) según regla de negocio, ingeniería de features con `StringIndexer` y `VectorAssembler` |
| **Entrenamiento** | Clasificación binaria con `RandomForestClassifier`, división en entrenamiento y prueba (`randomSplit`) |
| **Evaluación** | Métricas de `accuracy` y `areaUnderROC`, con análisis de decisiones técnicas (exclusión del monto para evitar data leakage) |

---

## Resultados

<div align="center">

| Métrica | Valor |
|:---:|:---:|
| **Accuracy** | `0.7812` |
| **Area Under ROC** | `0.8062` |

</div>

El AUC por sobre el accuracy sugiere que el modelo distingue bien entre transacciones riesgosas y normales en distintos umbrales, capturando patrones reales de compra (monto alto, horario de madrugada) y no solo la clase mayoritaria.

---

## Mejoras futuras

- [ ] Aplicar `CrossValidator` para ajustar `numTrees` y `maxDepth`
- [ ] Incorporar F1-score para balancear precisión y recall ante posible desbalance de clases

---

## Proyecto completo

El desarrollo completo (código comentado, evidencia del DataFrame y justificación técnica) está en:

**[`Modelo predictivo en Apache Spark MLlib.ipynb`](./Modelo%20predictivo%20en%20Apache%20Spark%20MLlib.ipynb)**

---

<div align="center">

Proyecto desarrollado como parte del bootcamp de Ciencia de Datos

</div>
