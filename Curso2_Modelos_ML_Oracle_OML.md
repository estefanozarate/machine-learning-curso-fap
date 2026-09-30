# Curso 2: Los 4 modelos clave de ML con Oracle Machine Learning on-premise

> **Entorno:** "Oracle Cloud on-premise" se interpreta como **Oracle Machine Learning (OML) ejecutándose dentro de Oracle Database en infraestructura propia**: una base 19c/23ai instalada localmente, o Exadata / Autonomous Database Cloud@Customer. El ML se ejecuta *in-database* con OML4SQL y OML4Py, sin sacar los datos del motor.

**Objetivo:** entrenar, evaluar y desplegar modelos dentro de Oracle Database, usando SQL y Python sobre los datos donde ya viven.

**Requisito previo:** Curso 1 (fundamentos estadísticos y proyecto House Prices).

---

## Módulo 0 – Arquitectura y entorno
- Qué es OML y por qué in-database: sin movimiento de datos, seguridad y escalabilidad del motor.
- Componentes: OML4SQL (paquete `DBMS_DATA_MINING`), OML4Py y OML4R.
- Opciones de despliegue: base 19c/23ai local, Exadata Cloud@Customer, Autonomous Database Cloud@Customer (incluye OML Notebooks y AutoML UI).
- Instalación del cliente OML4Py, usuarios y permisos.
- Carga del dataset de House Prices a tablas.

## Módulo 1 – Modelo 1: Regresión lineal y logística (GLM)
- Algoritmo Generalized Linear Model en OML.
- Regresión para predecir el precio de la vivienda.
- Clasificación binaria (por ejemplo, "precio sobre/bajo la mediana").
- Settings de regularización y preparación automática de datos (ADP).
- Interpretación de coeficientes y diagnósticos expuestos en las vistas del modelo.

## Módulo 2 – Modelo 2: Árboles de decisión y Random Forest
- Decision Tree como modelo interpretable (reglas legibles).
- Random Forest para mejorar la precisión.
- Hiperparámetros: profundidad, número de árboles, muestreo.
- Importancia de atributos.
- Comparación contra GLM usando el mismo dataset.

## Módulo 3 – Modelo 3: XGBoost
- Gradient boosting disponible en OML desde la versión 21c.
- Regresión y clasificación con XGBoost in-database.
- Ajuste de learning rate, profundidad y número de rondas.
- Por qué suele ser el modelo más fuerte en datos tabulares como House Prices.

## Módulo 4 – Modelo 4: K-Means (no supervisado)
- Clustering para segmentar viviendas o clientes.
- Elección de k e interpretación de centroides.
- Uso de los clusters como feature adicional en los modelos supervisados.

## Módulo 5 – Evaluación y despliegue en producción
- Scoring directo en SQL con `PREDICTION`, `PREDICTION_PROBABILITY` y `CLUSTER_ID`.
- Métricas de evaluación y matrices de confusión.
- Explicabilidad con `PREDICTION_DETAILS`.
- Versionado de modelos y reentrenamiento programado con `DBMS_SCHEDULER`.
- Exposición de predicciones a aplicaciones vía vistas o REST (ORDS).

## Módulo 6 – Proyecto final
Pipeline completo sobre House Prices dentro de Oracle:
1. Carga y preparación de datos.
2. Entrenamiento de los cuatro modelos.
3. Comparación de resultados contra el modelo Lasso del Curso 1.
4. Procedimiento almacenado que puntúa viviendas nuevas en tiempo real.

---

> Usar el mismo dataset que en el Curso 1 permite que el alumno llegue conociendo ya los datos y se concentre en la plataforma y los algoritmos.
