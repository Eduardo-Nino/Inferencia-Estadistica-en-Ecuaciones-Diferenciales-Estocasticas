# Modelo Hull & White (Información Completa)

## Descripción

Este proyecto implementa la estimación de parámetros del modelo de Hull & White utilizando **información completa** de la serie temporal de tasas de interés.

El **modelo de Hull & White** es un modelo estocástico de tasa de interés de la forma:

$$
dr_t = (\theta_t - a r_t) dt + \sigma dW_t
$$

donde:
- $r_t$ es la tasa de interés en el tiempo $t$,
- $\theta_t$ es la función que asegura ajuste a la curva de tasas,
- $a$ es la velocidad de reversión hacia la media,
- $\sigma$ es la volatilidad,
- $W_t$ es un proceso de Wiener estándar.

## Uso de información completa

En este escenario, todos los puntos de la serie temporal están disponibles para la estimación. Esto permite aplicar métodos de **máxima verosimilitud** sobre diferencias consecutivas de la serie (`r_t+1 - r_t`) para obtener estimadores de:

- $a$ (velocidad de reversión)
- $\theta$ (media de reversión)
- $\sigma$ (volatilidad)

Se realizan simulaciones usando **discretización tipo Euler**, y luego se calculan los estimadores para cada trayectoria simulada. Finalmente, se promedian los resultados para obtener valores representativos de los parámetros.

## Resultados esperados

La información completa proporciona estimadores más precisos y menos sesgados, ya que no se pierde ninguna observación. La tabla de resultados incluye las estimaciones promedio y puede compararse con los valores reales usados en la simulación.

## Uso

1. Simular series de tasas con `simular_euler`.
2. Estimar parámetros con `estimadores_HW`.
3. Generar tablas de resultados con promedios y desviaciones.
