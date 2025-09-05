# Modelo Hull & White (Información Reducida / Incompleta)

## Descripción

Este proyecto implementa la estimación de parámetros del modelo de Hull & White usando **información incompleta** de la serie temporal de tasas de interés.

El modelo sigue siendo:

$$
dr_t = (\theta_t - a r_t) dt + \sigma dW_t
$$

donde los parámetros tienen el mismo significado que en la versión con información completa.

## Uso de información incompleta

En este escenario, solo se dispone de un **subconjunto reducido de los datos** (por ejemplo, 10% de los puntos originales). Esto refleja situaciones en las que la frecuencia de observación es limitada o se pierden datos.

Para manejar la información reducida:

1. Se realiza la **estimación de parámetros usando regresión sobre los puntos disponibles**.
2. Se reconstruyen las trayectorias faltantes usando **puentes estocásticos** basados en los parámetros estimados de la serie reducida.
3. Se re-estiman los parámetros sobre la serie reconstruida para evaluar la efectividad de la reconstrucción.

## Resultados esperados

El uso de información incompleta puede introducir **mayor sesgo y variabilidad** en los estimadores. La reconstrucción mediante puentes estocásticos permite mitigar parcialmente esta pérdida de información y recuperar aproximaciones razonables de los parámetros originales.

## Uso

1. Seleccionar un subconjunto reducido de los datos (`r_reduc`).
2. Estimar parámetros con `estimadores_reducidos`.
3. Reconstruir la serie completa con `reconstruir_puentes`.
4. Estimar parámetros sobre la serie reconstruida y comparar con los valores reales.
