# Predicción de Cancelación de Clientes – Telecom X

Este proyecto tiene como objetivo predecir la cancelación (churn) de clientes de Telecom X, identificando los factores que más influyen y proponiendo estrategias de retención.

---
## Índice

1. [Contexto](#1-contexto)
2. [Variables más relevantes](#2-variables-mas-relevantes)
3. [Rendimiento de Modelos](#3-rendimiento-de-modelos)
4. [Insights y estrategias de retención](#4-insights-y-estrategias-de-retencion)
5. [Conclusión](#5-conclusion)
6. [Tecnologías Utilizadas](#6-tecnologias-utilizadas)

---
## 1. Contexto

Se realizó un análisis predictivo para identificar clientes con mayor probabilidad de cancelar sus servicios. El flujo de trabajo incluyó:

1. Limpieza y preparación de datos.
2. Codificación de variables categóricas (One-Hot Encoding).
3. Balanceo de clases mediante **oversampling**.
4. Análisis de correlación para variables numéricas y categorizadas.
5. División de la data y entrenamiento de modelos de clasificación: **Random Forest (RF), K-Nearest Neighbors (KNN)** y un modelo de referencia **Dummy**.
6. Evaluación del rendimiento y análisis de la importancia de las variables.

---

## 2. Variables más relevantes

### Análisis de correlación

| Variable                        | Correlación con churn |
| ------------------------------- | --------------------- |
| antiguedad_meses                | -0.414                |
| tipo_contrato_Two year           | -0.391                |
| servicio_internet_Fiber optic   | 0.336                 |
| metodo_pago_Electronic check    | 0.330                 |
| cargo_total                      | -0.241                |
| cargo_mensual                    | 0.220                 |

**Conclusión:** Las variables con mayor correlación absoluta influyen más directamente en la cancelación.

### Importancia de variables según los modelos

#### Random Forest

| Variable                 | Importancia |
| ------------------------ | ----------- |
| cargo_mensual           | 0.196       |
| cargo_total             | 0.173       |
| tipo_contrato_Two year  | 0.153       |
| antiguedad_meses        | 0.106       |
| tipo_contrato_One year  | 0.104       |

#### KNN

| Variable                 | Importancia |
| ------------------------ | ----------- |
| tipo_contrato_Two year  | 0.018       |
| antiguedad_meses        | 0.017       |
| cargo_total             | 0.009       |
| tipo_contrato_One year  | 0.009       |

**Conclusión:** Coincidiendo parcialmente con la correlación, **tipo de contrato, antigüedad y cargos** son los factores clave.

---

## 3. Rendimiento de los modelos

| Modelo           | Accuracy |
| ---------------- | -------- |
| Dummy (baseline) | 0.50     |
| Random Forest    | 0.856    |
| KNN              | 0.759    |

**Observación:** Random Forest es el modelo con mejor desempeño, capturando relaciones no lineales e interacciones entre variables.

---

## 4. Insights y estrategias de retención

1. **Antigüedad y tipo de contrato**
   - Clientes con contratos largos y mayor antigüedad muestran menor churn.
   - Estrategia: Incentivar renovación de contratos y ofrecer beneficios para clientes de larga permanencia.

2. **Gasto mensual y total**
   - Clientes con cargos más altos tienen mayor riesgo de cancelar.
   - Estrategia: Proponer planes ajustados al consumo o promociones que aumenten la percepción de valor.

3. **Método de pago y servicio de Internet**
   - Pago electrónico y fibra óptica se asocian a mayor churn.
   - Estrategia: Implementar recordatorios de pago, soporte personalizado y mejoras en la experiencia de Internet.

---

## 5. Conclusión

El análisis confirma que **antigüedad, tipo de contrato, cargos y servicios contratados** son los factores más relevantes para predecir la cancelación.  
Implementar estrategias de retención personalizadas permitirá reducir significativamente el churn y mejorar la satisfacción de los clientes.

## 6. Tecnologías Utilizadas
* **Python**: Análisis y procesamiento de datos.
* **Pandas y Numpy**: Manipulación de datos.
* **Matplotlib y Seaborn**: Visualización de datos.
* **scikit-learn**: Modelado predictivo, escalado, codificación y evaluación de modelos.
* **imblearn (RandomOverSampler)**: Balanceo de clases para datasets desbalanceados.
* **Google Colab**: Documentación y presentación del análisis.


