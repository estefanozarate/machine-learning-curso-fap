# Curso 1: Fundamentos estadísticos para Machine Learning

**Objetivo:** construir la base estadística mínima para entender qué hace un modelo, y cerrar con un proyecto de regresión sobre *House Prices – Advanced Regression Techniques* de Kaggle, ejecutado en **Google Colab**.

**Herramientas:** Python, pandas, NumPy, matplotlib/seaborn, SciPy, statsmodels y scikit-learn (todas preinstaladas en Colab).

---

## Módulo 1 – Datos y estadística descriptiva
- Tipos de variables: numéricas, categóricas y ordinales.
- Medidas de tendencia central y de dispersión.
- Percentiles, IQR y detección de outliers.
- Visualización: histogramas, boxplots y scatterplots.
- Práctica con pandas y matplotlib/seaborn.

## Módulo 2 – Probabilidad
- Espacio muestral, eventos, reglas de suma y producto.
- Probabilidad condicional e independencia.
- Teorema de Bayes.
- Variables aleatorias, esperanza y varianza.

## Módulo 3 – Distribuciones
- Bernoulli, binomial, Poisson, uniforme y normal.
- Asimetría y curtosis.
- Q-Q plots para evaluar normalidad.
- Transformaciones (log, Box-Cox) para corregir sesgo; se aplicarán luego a `SalePrice`.

## Módulo 4 – Inferencia estadística
- Población vs. muestra.
- Teorema central del límite.
- Intervalos de confianza.
- Pruebas de hipótesis: t-test, chi-cuadrado y ANOVA.
- p-valor y errores tipo I / tipo II.

## Módulo 5 – Correlación y regresión lineal
- Covarianza, correlación de Pearson y de Spearman.
- Regresión lineal simple y múltiple por mínimos cuadrados.
- Interpretación de coeficientes y R² (incluida la interpretación con objetivo en logaritmo).
- Supuestos: linealidad, homocedasticidad, normalidad de residuos, multicolinealidad (VIF).
- Análisis de residuos.

## Módulo 6 – Puente hacia el Machine Learning
- Train/test split y validación cruzada (k-fold).
- Sesgo vs. varianza; overfitting y underfitting.
- Métricas de regresión: MAE, RMSE y R².
- Regularización: Ridge (L2) y Lasso (L1).
- Escalado de variables.
- Descenso de gradiente (nivel intuitivo).

---

## Módulo 7 – Proyecto final: House Prices (Kaggle) en Google Colab

El proyecto se desarrolla íntegramente en **Google Colab** con el notebook `Curso1_Proyecto_HousePrices.ipynb`, que se ejecuta celda por celda (`Shift + Enter`). Cada sección del notebook indica qué módulo del curso está aplicando. No requiere instalar nada ni usar GPU.

**Obtención de los datos** (tres opciones dentro del notebook): copia pública del dataset en GitHub, API oficial de Kaggle con `kaggle.json`, o subida manual de `train.csv` y `test.csv`.

**Etapas del proyecto:**

1. **Estadística descriptiva:** medidas de `SalePrice`, outliers por IQR, histogramas y boxplots.
2. **Distribución y transformación:** asimetría, curtosis, Q-Q plots y transformación logarítmica del precio.
3. **Inferencia:** intervalo de confianza del precio medio, prueba t (aire acondicionado central) y ANOVA (calidad general).
4. **Correlación:** ranking de variables más correlacionadas, heatmap, Pearson vs. Spearman y detección de outliers en `GrLivArea`.
5. **Regresión lineal clásica:** modelo simple y múltiple con statsmodels, interpretación de coeficientes, residuos y VIF.
6. **Limpieza:** tratamiento de nulos según su significado (por ejemplo, `NaN` en `PoolQC` significa "no tiene piscina"), con valores de relleno aprendidos solo del train.
7. **Feature engineering:** superficie total, baños totales, antigüedad, corrección de asimetría con `log1p` y one-hot encoding.
8. **Modelado:** regresión lineal, Ridge y Lasso comparados con validación cruzada de 5 pliegues.
9. **Evaluación:** holdout del 20%, RMSE en log, MAE en dólares, R², gráfico predicho vs. real y residuos.
10. **Interpretación de la predicción:** descomposición de la predicción de una casa en intercepto + aporte de cada variable.
11. **Simulador:** modificar una casa (calidad, área, garaje) y observar el cambio en el precio estimado.
12. **Entrega:** generación de `submission.csv` y envío a Kaggle con la métrica oficial (RMSE sobre el logaritmo del precio).

**Resultado de referencia:** con Lasso se obtiene un RMSE(log) cercano a **0.11** en validación cruzada, es decir, un error medio de alrededor del 11% del precio.

**Ejercicios de cierre:** variar el umbral de asimetría, crear variables de interacción, promediar Ridge y Lasso, repetir pruebas de hipótesis con otras variables y explorar el simulador.
